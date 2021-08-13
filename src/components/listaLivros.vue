<template>
  
  <table>
    <tr v-for="(livro, index) in livros" :key="index">
      <td v-for="(item, index) in livro" :key="index">
        {{ item }}
        <!-- <input v-model="livro.checked" type="text" />
        <label>{{ item }} </label> -->
      </td>
    </tr>
  </table>
</template>

<script>
export default {
  props: {
    livros: {
      type: Array,
      defalt() {
        return [{ título: "Lista vazia" , autor: "inexistente"}];
      },
    },
  },
};
</script>

<style>
</style>
