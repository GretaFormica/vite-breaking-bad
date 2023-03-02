<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
    }
  },

  emits: ["on-alien"],

    methods: {
        alien() {
        this.$emit("on-alien");
        },
    },
};
</script>

<template>
  <div class="container-m">
        
        <button @click="alien">search only alien</button>

    </div>
</template>

<style lang="scss" scoped>
.container-m{
    max-width: 1200px;
    margin: 0 auto;

    button{
        padding: 5px;
    }
}



</style>