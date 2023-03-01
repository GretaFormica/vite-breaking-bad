<script>
import Header from './components/Header.vue';
import axios from "axios";

export default {
  data() {
    return {
      cards: []
    }
  },

  components: {
    Header
  },

  created() {
    axios
    .get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0")
    .then((respnse) => {
      this.cards = response.data.results;
    })
  }
}

</script>

<template>

  <Header />
  
</template>

<style lang="scss">
@use "./components/style.scss"
</style>
