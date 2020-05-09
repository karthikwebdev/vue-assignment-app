<template>
    <div class="todo-item" v-bind:class="{'is-complete':todo.completed}">
        <p>
            <input type="checkbox" v-on:change="markComplete" v-bind:checked="todo.completed">
            {{todo.title}}
            <button 
            @click="$emit('del-todo',todo.id)" 
            class="del">x</button>
        </p>
    </div>
</template>

<script>
export default {
    name:"TodoItem",
    props:["todo"],
    methods:{
        markComplete(){
            this.todo.completed = !this.todo.completed
        }
    }
}
</script>

<style scoped>
    .todo-item{
        margin:0 20vw;
        background: #f4f4f4;
        padding: 10px;
        border-bottom: 3px #ccc double;
    }

    .is-complete{
        text-decoration: line-through;
    }

    .del{
        font-size: 1rem;
        color:black;
        border: none;
        padding: 5px 10px;
        cursor: pointer;
        float: right;
    }
</style>

