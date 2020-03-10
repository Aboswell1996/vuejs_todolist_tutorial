<template>
    <div>
        <div v-bind:key="todo_item.id" v-for="todo_item in todo_array">
            <TodoItem v-bind:todoitem="todo_item" v-on:del-todoitem="$emit('del-todoitem',todo_item.id)"/>
        </div>

    </div>
</template>


<script>

import TodoItem from './TodoItem.vue';

export default {
    name: "Todos",
    //props : ['temp1']
    components:{
        TodoItem
    },
    props: {
        "todo_array": Array
    }
}
</script>

<style scoped>

</style>