<template>
    <div class="todo-item" v-bind:class="{'is-complete': task.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
                {{task.title}}
            <button @click="$emit('del-todo', task.id)" class="del">
                x
            </button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["task"],
    methods: {
        markComplete() {
            this.task.completed = !this.task.completed
        }
    }
}
</script>


<style scoped>
    .todo-item {
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 1px #ccc dotted;
    }

    .is-complete {
        text-decoration: line-through;
    }

    .del {
        background: #ff0000;
        color: #fff;
        border: none;
        padding: 5px 9px;
        border-radius: 50%;
        cursor: pointer;
        float: right;
    }
</style>