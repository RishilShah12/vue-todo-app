<template>
    <ul>
        <li v-for="todo in todos" :key="todo.text">
            <todo-view :todo="todo" @deleteTodo="(data) => this.$emit('deleteTodo', data)" />
        </li>
    </ul>
</template>

<script>
import TodoView from './TodoView.vue';

export default {
    props: ['todos'],
    components: {
        TodoView,
    },
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