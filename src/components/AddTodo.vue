<template>
    <div>
            <h1>Todo App</h1>
        <form @submit="addTodo">
            <input type="text" v-model="title" name="title" placeholder="Add todo...">
            <input type="submit" value="Submit" class="btn">
        </form>
        <p>*Adding Todo may take a few seconds as it is a free Rest api</p>
    </div>
</template>

<script>

export default {
    name:"AddTodo",
    data(){
        return {
            title:""
        }
    },
    methods:{
        addTodo(e){
            e.preventDefault()
            const newTodo = {
                title:this.title,
                completed:false   
            }
            this.$emit('add-todo',newTodo)
            this.title = ""
        }
    }
}
</script>

<style scoped>
    form{
        display: flex;
        margin: 0 20vw;
    }
    input[type = "text"]{
        flex:10;
        padding: 15px;
    }

    input[type = "submit"]{
        flex:4;
        padding: 5px;
    }
    p{
        padding:20px 0;
        margin:0 20vw;
        text-align: center;
    }
    h1{
        text-align: center;
        padding:40px;
    }
</style>