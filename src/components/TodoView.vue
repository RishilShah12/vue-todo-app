<template>
    <div>
        <input type="checkbox" :checked="this.isChecked" v-model="checke">
        <p :class="completedClass">{{ todo.text }}</p>
    </div>
</template>

<script>

export default {
    props: ['todo', 'isChecked'],
    data() {
        return {
            checke: this.isChecked,
        }
    },
    computed: {
        completedClass() {
            return {
                strike: this.checke
            }
        },
    }
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