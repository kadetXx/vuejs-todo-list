<template>
  <div class="todo-item">
    <p v-bind:class="{'is-complete' : todo.completed}">
      <input class="check" v-on:change="markComplete" type="checkbox">
      {{todo.title}}
      <i class="fas fa-trash-alt" @click="$emit('del-todo', todo.id)"></i>
    </p>
  </div>  
</template>

<script>
export default {
  name: 'TodoItem',
  props: ['todo'],
  methods: {
    markComplete() {
      this.todo.completed = !this.todo.completed;
    }
  }
}
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 15px;
    border-bottom: 1px solid #ccc;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .check {
    margin-right: 10px;
  }

  .fa-trash-alt {
    float: right;
    color: #2c3e50;
  }
</style>