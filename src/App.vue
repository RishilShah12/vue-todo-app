<template>
  <h1 id="heading">Todo List</h1>
  <create-todo />
  <todo-lists />
</template>

<script>
import CreateTodo from './components/CreateTodo.vue';
import TodoLists from './components/TodoLists.vue'

export default {
  components: {
    CreateTodo,
    TodoLists,
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