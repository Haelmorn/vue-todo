<template>
    <div>
        <div v-bind:key="task.id" v-for="task in todo_data">
            <TodoItem v-bind:task="task" v-on:del-todo="$emit('del-todo', task.id)"/>
        </div>
    </div>
</template>

<script>

import TodoItem from './TodoItem'
export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todo_data"]
}
</script>

<style scoped>

</style>