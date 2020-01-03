<template>
    <div>
        <link rel="stylesheet" href="/build/tailwind.css">
        <div v-bind:key="todo.id" v-for ="todo in todos">
        <TodoItem class="w-full rounded overflow-hidden shadow-lg" v-bind:todo ="todo" v-on:del-todo="$emit('del-todo',todo.id)" />
        <!--<h3 class="text-4xl font-bold text-center text-blue-500">{{todo.title}}</h3>-->
    </div>
    </div>
</template>

<script>
import TodoItem from "./Todoitem"
export default {
    name:"todos",
    components:{
        TodoItem
    },
    props:["todos"]
}
</script>

<style scoped>

</style>