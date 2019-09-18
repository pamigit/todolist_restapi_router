<template>
  <div class="home">
    <Header />
    <Todos v-bind:todos="todos" v-on:del-todo="delTodo"/>
  </div>
</template>

<script>
// @ is an alias to /src
import Todos from "../components/Todos";
import Header from "../components/layout/Header"

export default {
  name: 'home',
  components: {
    Todos,
    Header
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Wash car",
          completed: false
        },
        {
          id: 2,
          title: "Go to dentist",
          completed: false
        },
        {
          id: 3,
          title: "Buy pampers",
          completed: false
        }
      ]
    }
  },
  methods: {
    delTodo(id) {
        this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style scoped>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }
</style>