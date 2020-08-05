<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
        <TodoItem v-bind:todo="todo" v-on:del-todo="deleteTodo"/>
    </div>
  </div>
</template>

<script>
import TodoItem from './TodoItem'
export default {
    components: {
        TodoItem
    },
    name: "Todos",
    props: ["todos"],
    methods: {
      deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id)
      }
    },
}
</script>

<style scoped>

</style>