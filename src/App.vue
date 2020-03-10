<template>
  <div id="app">
    <Todos v-bind:todo_array="todos_array_from_data" v-on:del-todoitem="deleteTodo"/>
  </div>
</template>

<script>

import Todos from './components/Todos'

export default {
  name: 'App',
  components: {
    Todos
  },
  data(){
    return{
      todos_array_from_data: [
        {
          id: 1,
          title: "item1",
          completed: true
        },
        {
          id: 2,
          title: "item2",
          completed: true
        },
        {
          id: 3,
          title: "item3",
          completed: false
        }
      ]
    }
  },
  methods:{
    deleteTodo(id){
      console.log("Dsad")
      this.todos_array_from_data = this.todos_array_from_data.filter(todo_iter => todo_iter.id !== id)
    }
  }
}
</script>

<style>

</style>
