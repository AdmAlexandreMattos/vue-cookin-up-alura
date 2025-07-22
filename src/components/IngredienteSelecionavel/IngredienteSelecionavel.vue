<script lang="ts">
import Tag from "../Tag/Tag.vue";

export default {
  name: "IngredienteSelecionavel",
  components: {
    Tag,
  },
  props: {
    ingrediente: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      selecionado: false,
    };
  },
};
</script>

<template>
  <button
    class="ingrediente"
    @click="selecionado = !selecionado"
    :aria-pressed="selecionado"
  >
    <Tag :texto="ingrediente" :ativa="selecionado" />
  </button>
</template>

<style scoped>
.ingrediente {
  cursor: pointer;
}
</style>
