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
        console.log(this.cards);
    })
  }
}

</script>

<template>
    <div class="row row-cols-5">
        <div class="col" 
            v-for="card in cards">

            <h3>{{ card.name }}</h3>
        </div>
    </div>
  
</template>

<style lang="scss">


</style>