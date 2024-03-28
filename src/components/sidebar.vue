<template>
  <div>
    <div id="sidebar" >
      <img id="image" src="/src/assets/Ai.png" alt="logo">
        <h2 id="heading"> Chats</h2>
        
        <ul id="list">
            <li v-for="(i,index) in chats" :key="index">{{index+1}} {{i}}</li>
        </ul>
        <div>
        <Header></Header>
        </div>
      </div>
  
</div>

  </template>
  
  <script>
  import Header from "./header.vue"
 
  export default {
    components:{
      "Header":Header
    },
    props:['chats'],
    data () {
      return {     
      }
    },
    methods:{
      
    }
  }
  </script>
<style scoped>
#sidebar{
  border-right: 1px solid black;
  position: fixed;
  height: 100%;
  width: 170px;
  justify-content: left;
  top: 0;
  left: 0;
  padding: 20px;
  background-color:#4b48484b;
  color:black;
}

#heading{
  color: black;
  font-family: 'Andale Mono, monospace';
  font-size:x-large;
}
#image{
  height: 100px;
  width: 100px;
}
#list{
  display: flex;
  flex-direction: column;
  gap: 2px;
}
</style>