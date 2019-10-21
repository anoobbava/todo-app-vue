<template>
<div class="new-todo">
  <input type="text" v-model="todo">
  <br/>
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
        if(this.todo !== '') {
          this.$emit('clicked', this.todo);
          this.todo = '';
        }
        
      }
    }
  }
</script>

<style>
  .new-todo {
    margin: auto;
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    font-size: 18px;
  }
</style>