<template>
    <div>
        <div v-for="todo in todos" v-bind:key="todo.id" class="list-group-item todo-item">
            <TodoItem v-on:del-todo="$emit('del-todo', todo.id)" v-bind:todo="todo" />
        </div>
    </div>
</template>

<script>
import TodoItem from "./TodoItem"
export default {
    name: "Todos",
    components: {
        TodoItem
    },
    props: ["todos"]
}
</script>

<style scoped>
    .todo-item {
        background: #f4f4f4;
    }
</style>