<script lang="ts">
import SelecionarIngredientes from "../SelecionarIngredientes/SelecionarIngredientes.vue";
import ListaIngredientesUsuario from "../ListaIngredientesUsuario/ListaIngredientesUsuario.vue";
import MostrarReceitas from "../MostrarReceitas/MostrarReceitas.vue";

type Pagina = "SelecionarIngredientes" | "MostrarReceitas";

export default {
  data() {
    return {
      ingredientes: [] as string[],
      conteudo: "SelecionarIngredientes" as Pagina,
    };
  },
  components: {
    SelecionarIngredientes,
    ListaIngredientesUsuario,
    MostrarReceitas,
  },
  methods: {
    adicionarIngrediente(ingrediente: string) {
      this.ingredientes.push(ingrediente);
    },

    removerIngrediente(ingrediente: string) {
      this.ingredientes = this.ingredientes.filter(
        (iLista) => ingrediente !== iLista
      );
    },

    navegar(pagina: Pagina) {
      this.conteudo = pagina;
    },
  },
};
</script>

<template>
  <main class="conteudo-principal">
    <ListaIngredientesUsuario :ingredientes="ingredientes" />

    <SelecionarIngredientes
      v-if="conteudo === 'SelecionarIngredientes'"
      @ingrediente-selecionado="adicionarIngrediente($event)"
      @ingrediente-removido="removerIngrediente($event)"
      @buscar-receitas="navegar('MostrarReceitas')"
    />

    <MostrarReceitas
      v-else-if="conteudo === 'MostrarReceitas'"
      @editar-receitas="navegar('SelecionarIngredientes')"
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
