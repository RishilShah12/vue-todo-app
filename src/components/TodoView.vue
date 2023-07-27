<template>
    <div @mouseover="this.isVisible = true" @mouseout="this.isVisible = false">
        <input type="checkbox" v-model="checked">
        <p :class="completedClass">{{ todo.text }}</p>
        <button @click.prevent="deleteTodo" :class="{ visible: isVisible }">Delete</button>
    </div>
</template>

<script>

export default {
    props: ['todo'],
    data() {
        return {
            checked: this.todo.isChecked,
            isVisible: false,
        }
    },
    computed: {
        completedClass() {
            return {
                strike: this.checked
            }
        },
    },
    methods: {
        deleteTodo() {
            this.$emit('deleteTodo', {
                text: this.todo.text,
                isChecked: this.checked
            })
        }
    }
}
</script>

<style scoped>
div {
    width: 500px;
    display: grid;
    grid-template-columns: 1fr 10fr 1fr;
    background-color: rgb(195, 195, 195);
}

button {
    border: 0px;
    background-color: rgb(195, 195, 195);
    color: rgb(195, 195, 195);
}

.visible {
    background-color: rgb(207, 207, 207);
    color: black;
}

.strike {
    text-decoration: line-through;
}
</style>