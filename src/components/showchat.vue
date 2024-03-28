<template>
    
  <div id="chatbox">
   
    <!-- <Header></Header> -->
    <input type="text" id="chat" v-model="message" @keyup.enter="sendMessage" placeholder="Enter your text here">
    <div id="text" v-if="generatedText">
    {{ generatedText }}
    </div>
  </div>

</template>

<script>

import runChat from '../api';
import Header from  './header.vue'

export default {
  components:{"Header":Header},
  data() {
    return {
      message: '',
      generatedText: ''
    }
  },
  methods: {
       async generateText() {
      
      if (this.message.trim() !== '') {
        try {
          // // Assuming runChat returns generated text asynchronously
          // // runChat(this.message)
          // // .then(response=>{ this.generatedText=response
          // //   console.log(response)
          this.generatedText= await runChat(this.message)
          console.log(this.generateText)
          // })
        
        } catch (error) {
          console.error('Error generating text:', error);
        }
      }
    },
    sendMessage() { 
      if (this.message.trim() !== '') {
        this.$emit('new-message', this.message);
       
        this.generateText(); // Call generateText after sending message
        this.message = '';
      }
    }
  },

};
</script>

<style scoped>
.box{
  display: flex;
  justify-content: center;
  align-items: center;
}

#text{
  border-radius:2%;
  color:black;
  height: 50svh;
  position: relative;
  overflow-y: auto;
  background: rgb(245, 240, 240);
  margin-left: 100px;
  scrollbar-width: none;
  text-align:left;
  
}
#chat {
  /* border: 2px solid white; */
  background-color:#2c3848;
  color:#d2fafb;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 57%;
  margin-left: 107px;
  padding: 10px;
  position: fixed;
  bottom: 50px;
  border-radius: 10px;
  
}
#chatbox{
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 900PX;
  margin: auto;
 
}

</style>
