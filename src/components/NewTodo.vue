<template>
<div>
  <input type="text" v-model="todo">
  <button @click="createTodo">create todo</button>
</div>
</template>

<script>
  export default {
    data() {
      return {
        todo: ''
      }
    },

    methods: {
      createTodo() {
        this.$emit('clicked', this.todo);
        this.todo = '';
      }
    }
  }
</script>

<style>
</style>