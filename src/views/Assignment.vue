<template>
  <div>
    <h1>Assignment</h1>
    <div v-if="isNaN(input)">
      <p>Please enter only numbers..</p>
    </div>
    <div v-else>
    <h2>{{input*input*input}}</h2>
    </div>    
    <input type="text" v-model="input" name="number" placeholder="Type a number..." autofocus/>
  </div>
</template>

<script>
export default {
  name:"Assignment",
  data(){
    return{
      input:"" 
    } 
  }
}
</script>

<style scoped>
  h1{
    text-align: center;
    padding: 20px;
  }
  h2{
    height: 20vh;
    text-align: center;
    font-size: 5rem;
  }
  p{
    height: 20vh;
    text-align: center;
    font-size: 2rem;
    color: #fff;
    background-color: #333945;
    margin:0 20vw;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  input[type = "text"]{
    width:60vw;
    margin:0 20vw;
    padding: 10px;
    border: none;
    outline: none;
    border-bottom:2px solid black;
    font-size: 1rem;
    }
</style>
