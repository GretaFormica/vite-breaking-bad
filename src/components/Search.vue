<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  data() {
    return {
      title: "Hello world"
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
        
        <select class="p-1">
            <option>all</option>
            <option @click="alien">alien</option>
        </select>

    </div>
</template>

<style lang="scss" scoped>
.container-m{
    max-width: 1200px;
    margin: 0 auto;
}

</style>