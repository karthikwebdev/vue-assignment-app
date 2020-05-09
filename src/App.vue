<template>
  <div id="app">
    <Header/>
    <router-view/>
  </div>
</template>

<script>
import Header from "./components/Layouts/Header"
export default {
  components:{
    Header
  }
}
</script>
