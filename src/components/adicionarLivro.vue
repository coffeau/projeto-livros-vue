<template>
  <v-form v-model="valid">
    <v-container>
      <v-row>
        <v-col cols="12" md="3" >
          <v-text-field
            v-model="novoCampo.novoLivro"
            type="text"
            label="Livro"
            clearable
            rounded
            dense
            solo
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="3">
          <v-text-field
            v-model="novoCampo.novoAutor"
            label="Autor"
            type="text"
            clearable
            rounded
            dense
            solo
          >
            ></v-text-field
          >
        </v-col>
        <div data-app>
        <v-col cols="12" md="12">
          <v-autocomplete
            v-model="novoCampo.novaClass"
            :items="items"
            label="Selecione"
            rounded
            solo
            clearable
            small-chips
          ></v-autocomplete>
        </v-col>
        </div>
      </v-row>
        <span>
          <v-btn class="ma-2" outlined rounded @click="adicionarLivro">
            Adicionar
          </v-btn>
        </span>
    </v-container>
  </v-form>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      novoCampo: {
        novoLivro: "",
        novoAutor: "",
        novaClass: "",
      },
      items: ['Não lido', 'Completado', 'Lendo'],
    };
  },
  methods: {
    adicionarLivro() {
      this.$emit("adicionarLivro", this.novoCampo);
      this.novoCampo.novoLivro = "";
      this.novoCampo.novoAutor = "";
      this.novoCampo.novaClass = "";
    },
    ///        associarValor(value){
    ///          this.novaTarefa = value;
    ///        }
  },
};
</script>

<style>
</style>
