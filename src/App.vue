<template>
  <div id="app">
   <router-view></router-view>
</div>
</template>

<script>
import login from './components/login.vue'
import homepage from './components/homePage.vue'
export default {
  components:{
    'login-page': login,
    'home-page': homepage,
  },
  data () {
    return {     
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
