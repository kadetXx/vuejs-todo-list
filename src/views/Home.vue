<template>
  <div id="app">
    <Form v-on:addTodo='addTodo' />
    <Todos v-bind:Todos='Todos' v-on:del-todo="deleteTodo" />
  </div>
</template>

<script>

import Form from '../components/form'
import Todos from '../components/todos'
import axios from 'axios'

export default {
  name: "Home",
  components: {
    Form,
    Todos
  },

  data() {
    return {
      Todos: [],
    }
  },

  methods: {
    deleteTodo(id) {
      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
      .then(res => {
        this.Todos = this.Todos.filter(todo => todo.id !== id);
        console.log(res.data)
      })
      .catch(err => console.log(err))
    },

    addTodo(todo) {
      axios.post('https://jsonplaceholder.typicode.com/todos', {
        id: this.Todos.length + 1,
        title: todo,
        completed: false
      })
      .then(res => this.Todos = [...this.Todos, res.data])
      .catch(err => console.log(err))
      // this.Todos.push ({
      //   id: this.Todos.length + 1,
      //   title: todo,
      //   completed: false
      // })
    },
  },

  created() {
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=3')
    .then(res => {this.Todos = res.data})
    .catch(err => console.log(err))
  }

};
</script>

<style>
 * {
    margin: 0;
    padding: 0;
    --primary-color: #42b983;
  }
</style>
