<template>
    <div>
    <h1>This is the components from home</h1>
    <h1 v-if="show">{{data}}</h1>  
    <!-- defining properties -->
    <h1 v-else>You don't have any data.</h1>  
    <!-- applying if else statement (conditional statement) -->
    <h1>{{msg}}</h1> 
    <button v-on:click="hello('clicked')">submit</button> 
    <!-- calling event from method with parameter (data) -->
    
    <button v-on:click="display">toggle</button>
     <!-- toggling the method -->

    <h1>For loop in Vue.</h1>
    <table border="3px">
        <tr>
            <td>Id</td>
            <td>Name</td>
            <td>Email</td>
        </tr>
        <tr v-for="user in users" :key="user.id">
            <td>{{user.id}}</td>
            <td>{{user.name}}</td>
            <td>{{user.email}}</td>
        </tr>
    </table>
     
</div>
</template>

<script>

export default {
    name:'HomeComponent',
    props:{
        data:String,
        msg:String,
    }, 
    data(){
        return{
            users: [
                {id: 1, name: "manoj" , email:"test@mail"},
                {id: 2, name: "test" , email:"test@mail1"},
                {id: 3, name: "stranger" , email:"test@mail2"}
            ],
            show:true,
        }
    },
    methods:{
        hello(item){
            console.warn(item)
        },
        display(){
            this.show = !this.show 
        }  
    }
}
</script>