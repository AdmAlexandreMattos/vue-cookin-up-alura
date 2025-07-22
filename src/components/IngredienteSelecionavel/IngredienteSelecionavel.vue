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
  methods: {
    aoClicar() {
      this.selecionado = !this.selecionado;

      if (this.selecionado) {
        this.$emit("ingrediente-selecionado", this.ingrediente);
      }
    },
  },
  emits: ["ingrediente-selecionado"],
};
</script>

<template>
  <button class="ingrediente" @click="aoClicar()" :aria-pressed="selecionado">
    <Tag :texto="ingrediente" :ativa="selecionado" />
  </button>
</template>

<style scoped>
.ingrediente {
  cursor: pointer;
}
</style>
