<template>
    <div>
        <form @submit.prevent="newTask">
            <input type="text" v-model="title" name="title" placeholder="Add item...">
            <input type="submit" value="Submit" class="btn">
        </form>
    </div>
</template>

<script>
export default {
    name: "AddItem",
    data() {
        return {
            title: ""
        }
    },
    methods: {
        newTask() {
            const newItem = {
                title: this.title,
                completed: false,
            }
            this.$emit('add-todo', newItem);
            this.title=  ""
        }
    },
}
</script>

<style scoped>
    form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
</style>