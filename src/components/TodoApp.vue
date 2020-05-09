<template>
    <div>
        <AddTodo v-on:add-todo="addTodo" />
        <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" />
    </div>
</template>

<script>
import Todos from "./Todos";
import AddTodo from "./AddTodo";
export default {
  name: 'TodoApp',
  components: {
    AddTodo,
    Todos
},
data(){
  return {
    todos:[]
    }  
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
    addTodo(newTodo){
      fetch("https://jsonplaceholder.typicode.com/todos",{
        method:"POST",
         headers: {
          "Content-type": "application/json"
        },
        body:JSON.stringify(newTodo)
      })
      .then(res => res.json())
      .then(data => this.todos = [...this.todos, data])
      .catch(err => console.log(err))
    }
  },
  created(){
    fetch('https://jsonplaceholder.typicode.com/todos?_limit=5')
    .then(res=> res.json())
    .then(data => this.todos = data)
    .catch(err => console.log(err))
  }
}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    }

  body{
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.4;
      }
  .btn{
    border:none;
    background-color: #555;
    color: #fff;
    font-size: 1rem;
  }
  .btn:hover{
    background-color: #777;
  }
</style>
