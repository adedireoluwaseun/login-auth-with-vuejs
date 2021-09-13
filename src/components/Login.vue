<template>
  <h2>Login</h2>
  <div @submit.prevent="handleSubmit" class="form-group">
      <label for="">Email</label>
      <input type="email" class="form-control" v-model="email" placeholder="Email"/>
  </div>
   <div class="form-group">
      <label for="">password</label>
      <input type="password" class="form-control" v-model="password" placeholder="password "/>
  </div>
  <button class="btn btn-primary btn-block" >Login</button>
</template>

<script>
import axios from 'axios'
export default {
 name:"Login",
 data(){
  return{
      email:'',
      password:'',
  }
 },
 methods:{
     async handleSubmit(){
       const response = await axios.post('login',{
           email:this.email,
           password: this.password,
       })
       console.log(response);
     }
 }
}
</script>

<style>

</style>