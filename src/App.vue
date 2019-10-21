<template>
  <div id="app">
    <Todos/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
export default {
  name: 'app',
  components: {
    Todos
  }
}
</script>

<style>
body {
    background-color: whitesmoke;
}
</style>
