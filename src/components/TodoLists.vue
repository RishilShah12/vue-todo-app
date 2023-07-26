<template>
    <ul>
        <li v-for="(todo, index) in todos" :key="index">
            <todo-view :todo="todo" :is-checked="todo.isChecked" />
        </li>
    </ul>
</template>

<script>
import TodoView from './TodoView.vue';

export default {
    components: {
        TodoView,
    },
    created() {
        this.getTodos()
    },
    data() {
        return {
            todos: [],
        }
    },
    methods: {
        async getTodos() {
            let res = await fetch('todos.json');
            let data = await res.json();
            this.todos = data;
        },

        // pushTodos() {
        // this.todos.push()
        // }
    }
}
</script>

<style scoped>
p {
    text-align: left;
    margin-left: 10px;
}

li {
    margin-bottom: 15px;
}

ul {
    list-style-type: none;
    padding-left: 0px;
}
</style>