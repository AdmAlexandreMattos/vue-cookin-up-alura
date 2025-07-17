<script lang="ts">
import Banner from "./components/Banner/Banner.vue";
import ConteudoPrincipal from "./components/ConteudoPrincipal/ConteudoPrincipal.vue";

export default {
  name: "App",
  components: {
    Banner,
    ConteudoPrincipal,
  },
};
</script>

<template>
  <Banner />
  <ConteudoPrincipal />
</template>

<style scoped></style>
