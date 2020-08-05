<template>
 <div id="app">
   <h1>tugas hari ini yang telah selesai </h1>
   <AddTodos v-on:add-todo ="addTodo" />
 <Todos v-bind:todos="todos"  />
 </div>
</template>

<script>
import AddTodos from './components/AddTodo'
import Todos from './components/todos'
export default {
  name: 'App',
  components: {
    Todos,
    AddTodos
   
  },
  data() {
    return {
      count: 0,
     todos: [
       {
         id: 1,
         title: "farhan",
         completed: false
       },
       {
         id: 2,
         title: "ammar",
         completed: true
       },
       {
         id: 3,
         title: "dzakwan",
          completed: false
       },
     ]
    }
  },
  methods: {
    addTodo(newTodo){
      this.todos = [...this.todos, newTodo]
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  font-size: 22px;
  border-bottom: 1px solid blueviolet;
  background-color: aquamarine;
  color:  #2c3e50

  
}
</style>
