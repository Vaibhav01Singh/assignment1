<template>
    <div id="user">
        <button id="signOut" v-on:click="signOut">signOut</button>
    </div>
</template>
<script>
export default{
    components:{},
    data(){},
    methods:{
        signOut(){
            alert("Sign-Out Successfully")
        }
    }
}
</script>
<style scoped>
#user{
display: flex;
justify-content: space-between;
align-items: center;
}
#signOut{
    background-color: black;
    color: whitesmoke;
    margin-top: 300px;
    margin-left: 60px;
    
}
</style>