<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">

        <p><input type="checkbox" v-on:change="markComplete">
            {{todo.title}}
            <button @click="$emit('del-todo',todo,id)" 
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-1 px-4 rounded-full float-right">x</button>
            </p>
                
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
          this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
.todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }
  .is-complete {
    text-decoration: line-through;
  }
  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right;
  }
  
</style>