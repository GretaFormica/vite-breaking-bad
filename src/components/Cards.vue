<script>
import axios from "axios";
import Search from "./Search.vue";

export default {
  data() {
    return {
      cards: [],
      url: "https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0"
    }
  },

  components: {
    Search
  },

  created() {
    axios
    .get(this.url)
    .then((response) => {
        console.log(response)
        this.cards = response.data.data;
        // console.log(this.cards);
    })
  },

  methods: {
    FilteredPage() {
      this.url += "?race=alien"
    }
  }
}

</script>

<template>

  <Search @on-alien="FilteredPage" />

    <div class="row row-cols-5">
        <div class="col p-3" 
            v-for="card in cards">
            <div  class="bg">

                <img :src= card.card_images[0].image_url>
                <h5 class="text-center my-2">{{ card.name }}</h5>
                <p class="text-center"> {{ card.race }}</p>
            </div>
        </div>
    </div>
  
</template>

<style lang="scss">

.bg{
    background-color: #d48f38;
    height: 100%;
}


</style>