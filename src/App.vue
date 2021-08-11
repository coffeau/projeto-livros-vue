<template>
  <div class="container">
    <h2>{{ título }}</h2>

    <div class="input-group">
      <input @keyup.enter="adicionarTarefa" v-model="novaTarefa" type="text">
      <span>
        <button @click="adicionarTarefa" class="btn btn primary">Adicionar</button>
      </span>
    </div>
    <ul>
      <li v-for="(tarefa, index) in tarefas" :key="index" :class="{'removed': tarefa.checked}">
        <input v-model="tarefa.checked" type="checkbox">
        <label>{{ tarefa.título }}</label>
      </li>
    </ul>
    <footer>
      <em>Altere aqui o nome de sua lista de tarefas</em>
      <input v-model="título" type="text">
    </footer>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return{
      título: "Minha lista de tarefas",
      novaTarefa: "",
      tarefas: [
        {título: "Estudar", checked: false},
        {título: "Programar", checked: true},
      ]
    }
  },
  methods: {
    adicionarTarefa(){
      this.tarefas.push({
        título: this.novaTarefa,
        checked:false,
      })
      this.novaTarefa = ""
    }
  }
}

</script>

<style>
.container{
  width:40%;
  margin: 20px auto 20px auto;  
}

.removed{
 color:gray; 
}
.removed label{
  text-decoration: line-through;
}

ul li{
  list-style: none;
}
</style>
