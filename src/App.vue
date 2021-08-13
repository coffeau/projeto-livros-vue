<template>
  <section>
    <div class="container">
      <heather :valor="título"/>
      <adicionarLivro v-on:adicionarLivro="adicionarLivro" />
      <listaLivros :livros="livros" />
      <footer>
        <em>Altere aqui o nome de sua lista de livros</em>
        <entradaDados v-model="título" type="text" />
      </footer>
      </div>
  </section>
</template>

<script>

import heather from "@/components/heather";
import listaLivros from "@/components/listaLivros";
import adicionarLivro from "@/components/adicionarLivro";
import entradaDados from "@/components/templates/entradaDados"

export default {
  name: 'App',
  components: {heather, listaLivros, adicionarLivro, entradaDados},
  data(){
    return{
      título: "Minha lista de livros",
      novoLivro: "",
      livros: [
        {título: "A onda", autor: "Todd Strasser" },
        {título: "De Profundis", autor:"Oscar Wilde" },
      ]
    }
  },
  methods: {
    adicionarLivro(novoCampo){
      this.livros.push({
        título: novoCampo.novoLivro,
        autor: novoCampo.novoAutor
      })
    }
  }
}

</script>

<style>
.container{
  width:40%;
  margin: 20px auto 20px auto;  
}

ul li{
  list-style: none;
}
</style>
