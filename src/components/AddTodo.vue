<template>
  <div>
      <form @submit="addTodo" action="">
          <input type="text" v-model="title" name="title" placeholder="addTodo...">
          <input type="submit" value="submit" class="btn">
      </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'
export default {
    name: "Addtodos",
    data(){
        return {
            title: ''
        }
    },
    methods: {
        addTodo(e){
            e.preventDefault()
            const newTodo = {
                id: uuidv4(),
                title: this.title,
                completed: false
            }
            // send to parent
            this.$emit('add-todo', newTodo)
            this.title = ''
        }
    }

}
</script>

<style>
    input {
        padding: 10px;
       
    }
</style>