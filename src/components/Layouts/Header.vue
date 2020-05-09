<template>
    <header class="header">
        <h1>WELCOME</h1>
        <div>
            <router-link to="/">Todo App</router-link> |
            <router-link to="/assignment">Assignment</router-link>        
        </div>   
        </header>
</template>

<script>
export default {
    name:"Header"
}
</script>

<style scoped>
    .header{
        background-color: #333;
        color: #fff;
        text-align: center;
        padding: 10px;
        margin: 0 10vw 50px;
    }

    .header a{
        color: #fff;
        padding:20px;
        line-height: 50px;
    }


</style>