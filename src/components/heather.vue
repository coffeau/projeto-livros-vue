<template>
  <header>
      <h1>{{valor}}</h1>
  </header>
</template>

<script>
export default {
  props: ['valor']
};
</script>

<style scoped>
* {
  font-family: 'Quicksand', sans-serif;
}
</style>