<script>
import Cards from './Cards.vue';

export default {
  data() {
    return {
    }
  },

  components: {
    Cards
  },
}

</script>

<template>

    <div class="container-m">
        
        <select class="p-1">
            <option>alien</option>
        </select>

    </div>
    
    <div class="container">
        <Cards />
    </div>
  
</template>

<style lang="scss">

.container-m{
    max-width: 1200px;
    margin: 0 auto;
    margin-top: 50px;
}


</style>