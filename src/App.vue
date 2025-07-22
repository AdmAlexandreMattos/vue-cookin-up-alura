<script lang="ts">
import Banner from "./components/Banner/Banner.vue";
import ConteudoPrincipal from "./components/ConteudoPrincipal/ConteudoPrincipal.vue";
import Rodape from "./components/Rodape/Rodape.vue";

export default {
  name: "App",
  components: {
    Banner,
    ConteudoPrincipal,
    Rodape,
  },
};
</script>

<template>
  <Banner />
  <ConteudoPrincipal />
  <Rodape />
</template>

<style scoped></style>
