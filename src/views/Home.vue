<template>
  <div class="home">
    <Header />
    <div class="container">
      <AddTodo v-on:add-todo="addTodo"/>
      <Todos v-bind:todos="todos" v-on:del-todo="delTodo"/>
    </div>
  </div>
</template>

<script>
import Todos from "../components/Todos";
import Header from "../components/layout/Header";
import AddTodo from "../components/AddTodo";
import axios from "axios";

export default {
  name: 'home',
  components: {
    Todos,
    Header,
    AddTodo
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    delTodo(id) {
      axios.delete('https://jsonplaceholder.typicode.com/todos/${id}')
        .then(res => this.todos = this.todos.filter(todo => todo.id !== id))
        .catch(err => console.log(err));
    },
    addTodo(item) {
      if (item.title !== '') {
        axios.post('https://jsonplaceholder.typicode.com/todos', item)
          .then(res => this.todos = [...this.todos, res.data])
          .catch(err => console.log(err));
      }
    }
  },
  created() {
    axios.get("https://jsonplaceholder.typicode.com/todos?_limit=10")
      .then(res => this.todos = res.data)
      .catch(err => console.log(err));
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