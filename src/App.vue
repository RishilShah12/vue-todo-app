<template>
  <h1 id="heading">Todo List</h1>
  <create-todo @new-todo="pushTodo" />
  <todo-lists :todos="this.todos" />
</template>

<script>
import CreateTodo from './components/CreateTodo.vue';
import TodoLists from './components/TodoLists.vue'

export default {
  components: {
    CreateTodo,
    TodoLists,
  },
  // created() {
  //   this.getTodos()
  // },
  data() {
    return {
      todos: [
        {
          "text": "Todo #1 Do your Homework",
          "isChecked": true
        },
        {
          "text": "Todo #2 Complete Project",
          "isChecked": false
        }
      ]
    }
  },
  methods: {
    // async getTodos() {
    //   let res = await fetch('todos.json');
    //   let data = await res.json();
    //   this.todos = data;
    // },

    pushTodo(todoObj) {
      this.todos.unshift(todoObj)
    },
  }
}
</script>

<style>
* {
  font-family: 'Trebuchet MS', 'Lucida Sans Unicode', 'Lucida Grande', 'Lucida Sans', Arial, sans-serif;
}

#heading {
  font-size: 64px;
}
</style>