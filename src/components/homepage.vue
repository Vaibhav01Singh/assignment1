<template>
    <div id="homePage" >
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
        "sidebar":sidebar
    },
    data () {
      return {  
        chats:[]
      }
    },
    methods:{
        addMessage(message){
            this.chats.push(message)
        }
    }
  }
  </script>