<template>
    <div>
        <input type="checkbox" v-model="checked">
        <p :class="completedClass">{{ todo.text }}</p>
    </div>
</template>

<script>

export default {
    props: ['todo'],
    data() {
        return {
            checked: this.todo.isChecked,
        }
    },
    computed: {
        completedClass() {
            return {
                strike: this.checked
            }
        },
    },
}
</script>

<style scoped>
div {
    width: 500px;
    display: grid;
    grid-template-columns: 1fr 10fr;
    background-color: rgb(195, 195, 195);
}

.strike {
    text-decoration: line-through;
}
</style>