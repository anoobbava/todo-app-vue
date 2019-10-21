<template>
    <div>
      <ul>
        <div class="todo-list" v-for="todo in todos" :key=todo.title>
            <div class="todo-item">
              <input type="checkbox" v-model="todo.completed">
              <p v-bind:style="[todo.completed ? completedStyle : '']">
                {{todo.title}}
              </p>
            </div>
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
      ],

      completedStyle: {
        fontStyle: 'italic',
        textDecoration: 'line-through'
      }
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
  .todo-list {
    background-color: white;
    margin: auto;
    width: 50%;
    display: flex;
    flex-direction: column;
    align-items: center;
    box-shadow:
    /* The top layer shadow */
        0 1px 1px rgba(0,0,0,0.15),
            /* The second layer */
        0 10px 0 -5px #eee,
            /* The second layer shadow */
        0 10px 1px -4px rgba(0,0,0,0.15),
            /* The third layer */
        0 20px 0 -10px #eee,
            /* The third layer shadow */
        0 20px 1px -9px rgba(0,0,0,0.15);
    padding: 30px;
  }

  .todo-item {
    display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 0 20px 0;
    width: 70%;
    border-bottom: 1px solid #cecece;
    font-family: Roboto, sans-serif;
    font-weight: 100;
    font-size: 15px;
    color: #333333;
  }
</style>