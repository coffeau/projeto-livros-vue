<template>
  <div class="input-group">
    <!-- <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text" /> -->
    <!-- <entradaDados :valor="novaTarefa" @input="associarValor" /> -->
    <entradaDados @salvar="adicionarLivro" v-model="novoCampo.novoLivro"/>
    <entradaDados @salvar="adicionarLivro" v-model="novoCampo.novoAutor"/>
    <span>
      <button @click="adicionarLivro" class="btn btn primary">
        Adicionar
      </button>
    </span>
  </div>
</template>

<script>
import entradaDados from "@/components/templates/entradaDados";

export default {
    components: {entradaDados},
    data(){
        return{
          novoCampo: { novoLivro: "", novoAutor: ""},
        }
    },
    methods: {
        adicionarLivro(){
            this.$emit('adicionarLivro', this.novoCampo)
            this.novoCampo = "";
        },
///        associarValor(value){
///          this.novaTarefa = value;
///        }
    },
};
</script>

<style></style>
