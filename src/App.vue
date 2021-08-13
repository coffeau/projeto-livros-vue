<template>
  <section>
    <v-container class="container">
      <heather :valor="título" />
      <adicionarLivro v-on:adicionarLivro="adicionarLivro" />
      <v-card>
        <v-card-title>
          <v-text-field
            v-model="search"
            append-icon="mdi-magnify"
            label="Search"
            single-line
            hide-details
          >
          </v-text-field>
        </v-card-title>
        <v-data-table
          :headers="headers"
          :items="livros"
          :search="search"
          class="elevation-3"
        >
        </v-data-table>
      </v-card>
      <footer>
        <em>Altere aqui o nome de sua lista de livros</em>
        <entradaDados v-model="título" type="text" />
      </footer>
    </v-container>
  </section>
</template>

<script>
import heather from "@/components/heather";
import adicionarLivro from "@/components/adicionarLivro";
import entradaDados from "@/components/templates/entradaDados";

export default {
  name: "App",
  components: { heather, adicionarLivro, entradaDados},
  data() {
    return {
      título: "Minha Estante",
      novoLivro: "",
      novoAutor: "",
      novaClass: "",
      search: "",
      headers: [
        { text: "Livros", value: "título"},
        { text: "Autores", value: "autor" },
        { text: "Classificação", value: "lido"}
      ],
      livros: [
        { título: "A onda", autor: "Todd Strasser", lido: "Não lido" },
        { título: "De Profundis", autor: "Oscar Wilde", lido: "Completado" },
        { título: "Além do Carnaval", autor: "Jamens N. Green", lido: "Lendo"}
      ],
    }
  },

  methods: {
    adicionarLivro(novoCampo) {
      this.livros.push({
        título: novoCampo.novoLivro,
        autor: novoCampo.novoAutor,
        lido: novoCampo.novaClass
      });
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Quicksand&family=Raleway&display=swap');

.container {
  margin: 20px auto 20px auto;
}

ul li {
  list-style: none;
}

* {
  font-family: 'Raleway', sans-serif;
}

</style>
