<template>
  <div>
    <input type="text" class="new-todo" placeholder="Add new..." v-model="newTodo">
    <button class="add-btn" @click="$emit('addTodo', newTodo)" v-on:click="clearForm" v-bind:disabled="newTodo.length < 2">Add new</button>
  </div>
</template>

<script>

export default {
  name: 'Form',
  props: [],
  methods: {
   clearForm() {
     document.querySelector('input').value = '';
   }
  },

  data() {
    return {
      newTodo: ''
    }
  }
}
</script>

<style scoped>
  div {
    display: flex;
    align-items: center;
    /* border: 1px solid #2c3e50; */
    margin: 10px 20px;
    /* border-radius: 15px; */
    overflow: hidden;
  }

  .new-todo {
    width: 70%;
    padding: 5px;
    border: none;
    padding-left: 10px
  }

  .new-todo:focus {
    outline: none;
  }

  .add-btn {
    flex-grow: 1;
    height: 100%;
    background-color: #2c3e50;
    border-radius: 2px;
    color: #fff;
    border: none;
    padding: 7px 10px;
  }

   .add-btn:hover {
     background-color: #2e7c59;
   }

  .add-btn:focus {
    outline: none;
  }

</style>