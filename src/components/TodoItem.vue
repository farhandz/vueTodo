<template>
  <div id="tayo"  v-bind:class="{'is-complete': todo.completed}">
     <p> 
        <input type="checkbox" v-on:change="markComplete">
        {{todo.title}}
        <button @click="$emit('del-todo', todo.id)" >hapus</button>
     </p>
  </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: ["todo"],
    methods: {
      markComplete() {
         this.todo.completed = !this.todo.completed
        
      }
    }
}
</script>

<style scoped>
#tayo {
  width: 100px;
  height: 50px;
  border: 1px solid blue;
  margin: auto;
  margin-top: 16px;
  background-color: bisque;
  
}
.is-complete {
  text-decoration: line-through
}
button {
  height: 20px;
  color: white;
  background-color: blueviolet;
  border: 10px
}

</style>