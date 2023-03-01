<script>
import axios from "axios";

export default {
  data() {
    return {
      cards: []
    }
  },

  created() {
    axios
    .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
    .then((response) => {
        console.log(response)
        this.cards = response.data.data;
        // console.log(this.cards);
    })
  }
}

</script>

<template>
    <div class="row row-cols-5">
        <div class="col p-3" 
            v-for="card in cards">
            <div  class="bg">

                <img :src= card.card_images[0].image_url>
                <h5 class="text-center">{{ card.name }}</h5>
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