<script lang="ts">
import SelecionarIngredientes from "../SelecionarIngredientes/SelecionarIngredientes.vue";
import ListaIngredientesUsuario from "../ListaIngredientesUsuario/ListaIngredientesUsuario.vue";

export default {
  data() {
    return {
      ingredientes: [] as string[],
    };
  },
  components: { SelecionarIngredientes, ListaIngredientesUsuario },
  methods: {
    adicionarIngrediente(ingrediente: string) {
      this.ingredientes.push(ingrediente);
    },

    removerIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(
        (iLista) => ingrediente !== iLista
      );
    },
  },
};
</script>

<template>
  <main class="conteudo-principal">
    <ListaIngredientesUsuario :ingredientes="ingredientes" />

    <SelecionarIngredientes
      @ingrediente-selecionado="adicionarIngrediente($event)"
      @ingrediente-removido="removerIngrediente($event)"
    />
  </main>
</template>

<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #fffaf3);
  color: var(--cinza, #444);

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}
@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}
</style>
