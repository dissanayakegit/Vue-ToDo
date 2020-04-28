<template>
  <div id="app">
    <Todo v-bind:todos1="todos" v-on:del-item="deleteItem"></Todo>
  </div>
</template>

<script>

import Todo from './components/Todos'

export default {
  name: 'app',

  components: {
   Todo
  },

  data(){
    return {
      todos:[
        {
        title:"task 1",
        id:1,
        completed:true,
        },
        {
        title:"task 2",
        id:2,
        completed:true,
        },
        {
        title:"task 3",
        id:3,
        completed:false,
        },
      ]
    }
  },
  methods:{
    deleteItem(id){
      this.todos = this.todos.filter(todo => todo.id !== id);
    }
  }
}
</script>

<style>

</style>
