<script lang="ts">
import type ICategoria from "@/Interfaces/ICategoria";
import type { PropType } from "vue";

export default {
  name: "CardCategoria",
  props: {
    categoria: { type: Object as PropType<ICategoria>, required: true },
  },
};
</script>

<template>
  {{ categoria.nome }}
  {{ categoria.imagem }}
</template>
