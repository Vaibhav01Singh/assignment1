<template>
    <div id="homePage" >
      <img id="image2" src="/src/assets/Ai.png" alt="">
        <h1 id="help">How Can I Help You?</h1>
        <chat-box @new-message="addMessage"></chat-box>
        <sidebar :chats="chats"></sidebar>
    </div>
  </template>
  
  <script>
  import chatbox from "./showchat.vue"
  import sidebar from "./sidebar";
 
 
  export default {
    components:{
        "chat-box":chatbox,
        "sidebar":sidebar,
       
    },
    data () {
      return {  
        chats:[],
        
      }
    },
    methods:{
        addMessage(message){
            this.chats.push(message)
        }
    }
  }
  </script>
<style scoped>
#image2{
  height: 70px;
  width: 70px;
}
#help{
  text-align: center;
}
</style>