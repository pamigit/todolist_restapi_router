<template>
    <div>
        <form v-on:submit="addTodo">
            <input v-model="title" type="text" placeholder="Add todo ...">
            <input type="submit" value="Add Todo" class="btn btn-primary">
        </form>
    </div>
</template>

<script>
export default {
    name: "AddTodo",
    data() {
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e) {
            e.preventDefault();
            const newTodo = {
                title: this.title,
                completed: false
            };
            this.$emit('add-todo', newTodo);
            this.title = '';
        }
    }
}
</script>

<style scoped>
    form {
        display: flex;
        margin: 10px 0px;
    }
    input[type="text"] {
        flex: 10;
        padding: 5px;
        margin-right: 10px;
    }
    input[type="submit"] {
        flex: 2;
    }
</style>