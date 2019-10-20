<template>
    <div>
        <h2>Todos</h2>
        <ul>
          <div v-for="todo in todos" :key=todo.title>
            <input type="checkbox" :checked=todo.completed>{{todo.title}}
          </div>
        </ul>
        <NewTodo @clicked="fetchValueFromNewTodo"/>
    </div>
</template>

<script>
import NewTodo from './NewTodo.vue'
export default {
  data() {
    return {
      todos: [
        { title: 'wakeup', completed: true},
        { title: 'Make up Bed', completed: false},
        { title: 'Prayer', completed: false},
        { title: 'Exercise', completed: false},
        ]
    }
  },
  components: {
    NewTodo
  },
  methods: {
    fetchValueFromNewTodo(value) {
      this.todos.push({'title': value})
    }
  }
}
</script>

<style>
</style>