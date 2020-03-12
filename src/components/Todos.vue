<template>
    <div>
        <h1>To Dos</h1>
        <div v-bind:key="todo.id" v-for="todo in todos">
           <ToDoItem v-bind:todo="todo" v-on:del-todo="$emit('del-todo', todo.id)"/>
        </div>
    </div>
</template>

<script>
    import ToDoItem from './TodoItem.vue';
    
    export default {
        name: 'Todos',
        components: {
            ToDoItem
        },
        props: ["todos"]
    }
</script>

<style scoped>
</style>