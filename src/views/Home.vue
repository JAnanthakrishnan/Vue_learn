<template>
  <div id="app">
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo" v-on:mark-complete="markComplete"/>
  </div>
</template>

<script>
import Todos from '../components/Todos'
import AddTodo from '../components/AddTodo'
export default {
  name: 'App',
  components: {
    Todos,
    AddTodo
  },
  data() {
    return {
      msg: 'Hello',
      todos: [
      {
        id: 1,
        title: 'Take out the trash',
        completed: false
      },
      {
        id: 2,
        title: 'Dinner with wife',
        completed: false
      },
      {
        id: 3,
        title: 'Meeting with boss', 
        completed: false
      }
    ],
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id!==id)
    },
    markComplete(id) {
      this.todos = this.todos.map((todo) => { 
        if(todo.id===id)
          todo.completed = !todo.completed
        return todo
      })
    },
    addTodo(newTodo){
      newTodo.id = this.todos.length+1;
      this.todos = [...this.todos,newTodo];
    }
  }
}
</script>

<style>
  *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body{
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
  .btn{
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover{
    background: #666;
  }
</style>
