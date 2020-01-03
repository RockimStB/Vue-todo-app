<template>
    <div class>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholer="Add Todo">
            <input type="submit" value="submit" class="bg-gray-600 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">
        </form>
    </div>
</template>

<script>
import uuid from 'uuid'
export default {
    name:"AddTodo",
    data(){
        return{
            title:''
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault();
            const newTodo ={
                id:uuid.v4(),
                title:this.title,
                completed:false
            }
            //send to parents 
            this.$emit('add-todo',newTodo);

            this.title= '';
        }
    }
}
</script>

<style scoped>
  form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
  
</style>