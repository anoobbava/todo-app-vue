<template>
    <div>
        <h2>Todos</h2>
        <ul>
          <div v-for="todo in todos" :key=todo.id>
            <input type="checkbox" :checked=todo.completed>{{todo.title}}
          </div>
        </ul>
        <NewTodo/>
    </div>
</template>

<script>
import NewTodo from './NewTodo.vue'
export default {
  data() {
    return {
      todos: [
        {id: 1, title: 'wakeup', completed: true},
        {id: 2, title: 'Make up Bed', completed: false},
        {id: 3, title: 'Prayer', completed: false},
        {id: 4, title: 'Exercise', completed: false},
        ]
    }
  },
  components: {
    NewTodo
  }
}
</script>

<style>
</style>