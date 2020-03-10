<template>
    <div class="todo-item" v-bind:class="{'is-complete':todoitem.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete">
            {{todoitem.title}}
            <button @click="$emit('del-todoitem', todoitem.id)" class ="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name: "TodoItem",
    props: {
        todoitem: Object
    },
    methods:{
        markComplete(){
            console.log(123)
            this.todoitem.completed =!this.todoitem.completed
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

.is-complete{
    text-decoration: line-through;
}

.del {
    background: red;
    color: #f4f4f4;
}

</style>