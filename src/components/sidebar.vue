<template>
  <div>
    <div id="sidebar" >
        <h3 id="heading"> Chats</h3>
        
        <ul>
            <li v-for="(i,index) in chats" :key="index">{{index+1}} {{i}}</li>
        </ul>
  </div>
  <button id="sign-out" @click="signout">Sign-Out</button>
</div>

  </template>
  
  <script>
 
  export default {
    props:['chats'],
    data () {
      return {     
      }
    },
    methods:{
      signout(){
        alert("signout")
      }
    }
  }
  </script>
<style scoped>
#sidebar{
  border-radius: 5%;
  margin-top: 10px;
  margin-left: 10px;
  border-right: 1px solid #f7de1c;
  position: fixed;
  min-height:500px;
  width: 100px;
  justify-content: left;
  top: 0;
  left: 0;
  padding: 20px;
  background-color:#2b2726;
  color: #f77754;
}
#sign-out{
  position: absolute;
  height: 50px;
  width: 70px;
  top: 10px;
  right: 20px;
}
#heading{
  color: chocolate;
  font-family: 'Andale Mono, monospace';
}
</style>