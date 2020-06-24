<template>
  <div>
    <div class="todos" v-bind:key="todo.uniqueId" v-for="todo in Todos">
      <TodoItem v-bind:todo='todo' v-on:del-todo="$emit('del-todo', todo.uniqueId)" />
    </div>
  </div>
</template>

<script>

import TodoItem from './todoItem'

export default {
  name: 'Todos',
  components: {
    TodoItem
  },
  props: ['Todos']
}
</script>

<style scoped>
  
</style>