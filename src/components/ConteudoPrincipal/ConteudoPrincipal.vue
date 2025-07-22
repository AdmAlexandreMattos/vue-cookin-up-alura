<script lang="ts">
import SelecionarIngredientes from "../SelecionarIngredientes/SelecionarIngredientes.vue";
import ListaIngredientesUsuario from "../ListaIngredientesUsuario/ListaIngredientesUsuario.vue";

export default {
  data() {
    return {
      ingredientes: ["Alho", "Manteiga", "Orégano"],
    };
  },
  components: { SelecionarIngredientes, ListaIngredientesUsuario },
};
</script>

<template>
  <main class="conteudo-principal">
    <ListaIngredientesUsuario :ingredientes="ingredientes" />

    <SelecionarIngredientes />
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
