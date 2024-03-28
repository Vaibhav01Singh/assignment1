<template>
    <div>

    <div id="login">
        <form >
            <h3 id="heading">LogIn</h3>
            Username: <input type="email" id="name" v-model="checkName" placeholder="Emal-id">
            <br>
            password: <input type="password" id="password" v-model="checkPassword" placeholder="****">
            <br>

            <button type="submit" id="signIn" v-on:click="error">SignIn</button>
        </form>
    </div>
  </div>
  </template>

  <script>

 export default {
    data () {
      return {
       name:"abc@gmail.com",
       password:"1234",
       checkName:"",
       checkPassword:""
      }
    },
    methods:{

      error:function(){
        if (this.name== this.checkName && this.password==this.checkPassword){
          alert("Logged in Successfully")
        } 
        else {
          alert("Invalid Username Or Password")
        }
    }
  }

    
  }
  </script>
  
  <style scoped>
  #logIn{
    font-weight: bold;
  }
  #login{
    background-color: beige;
    height: 200px;
    width: 300px;
    border:2px solid black;
    margin-left: 500px;
    margin-top: 150px;
     border-radius: 5% ;
 }
 #password{
    margin-top: 20px;

 }
 #signIn{
    margin-top: 20px;
 }
 #heading{
  color: rgb(21, 21, 222);
 }
  </style >
  