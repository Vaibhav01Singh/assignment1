<template>
  <div id="chatbox">
    <input type="text" id="chat" v-model="message" @keyup.enter="sendMessage" placeholder="Enter your text here">
    <div id="text" v-if="generatedText">
    {{ generatedText }}
    </div>
  </div>
</template>

<script>

import runChat from '../api';

export default {
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
#text{
  border-radius:2%;
  margin-top: 10px;
  color:whitesmoke;
  height: 70vh;
  overflow-y: auto;
  background: #283739;
  
}
#chat {
  /* border: 2px solid white; */
  background-color:#2c3848;
  color:#d2fafb;
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 50%;
  margin: auto;
  padding: 10px;
  position: fixed;
  bottom: 30px;
  
}
#chatbox{
  display: flex;
  flex-direction: column;
  justify-content: center;
  width: 50%;
  margin: auto;
  padding: 10px;
}

</style>
