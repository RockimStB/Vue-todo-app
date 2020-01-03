<template>
  <div id="app">
    <link rel="stylesheet" href="/build/tailwind.css"><!--Using this link allows tailwind css to be used simular to linking a css style sheet-->
     <Header/>
     <AddTodo v-on:add-todo="addTodo"/> <!--This call method addTodo-->
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
   
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'
import Header from './components/Header.vue'
import AddTodo from './components/AddTodo.vue'
//import axios from 'axios'//HTTP library to make post and get requests
export default {
  name: 'app',
  components: {
    //HelloWorld,
    Todos,
    Header,
    AddTodo,
  },
  data(){
    return {
      todos:[]
    }
  },
  //Methods in JS 
  methods:{
    deleteTodo(id){
        this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodo(newTodo){
      this.todos=[...this.todos, newTodo];
    }
  },
 /* created(){
    axios.get('https://jsonplaceholder.typicode.com/todos/1')
    .then(res=> this.todos=res.data)//used to handle promises
    .catch(err=> Console.error(err))//error to be  solved. Program does not accept console.log statements
  }*/
}
</script>

<style>
/* #app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}*/


  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: F69797;
    padding: 7px 20px;
    cursor: pointer;
  }
  .btn:hover {
    background: #666;
  }

</style>
