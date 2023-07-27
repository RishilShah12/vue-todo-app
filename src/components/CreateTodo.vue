<template>
    <div id="createTodo">
        <form autocomplete="off">
            <input type="text" id="todo" size="50" v-model="text">
            <button @click.prevent="createNewTodo">Create</button>
        </form>
    </div>
</template>

<script>
export default {
    data() {
        return {
            text: ''
        }
    },
    methods: {
        createNewTodo() {
            this.$emit('newTodo', {
                text: this.text,
                isChecked: false
            })
            this.text = ''
        }
    }
}
</script>

<style scoped>
div input,
div button {
    border: 0px;
    font-size: 24px;
}

#createTodo {
    display: inline-block;
    border: 1px solid rgb(4, 52, 47);
}
</style>