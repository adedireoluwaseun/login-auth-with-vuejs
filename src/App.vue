<template>
   <div id="app">
   
    
<i>"{{quote}}"</i>
<p>kanye west </p>
<button @click="createPost">Create Post</button>
   

     
   </div>
</template>

<script>
import axios from 'axios'
import {ref } from 'vue'


export default {
  name: 'App',
  setup(){
    const quote = ref('')
    const loadQuote = async () => {
      try{
          const response = await axios.get('https://api.kanye.rest/')
      quote.value = response.data.quote
      } catch (err){
        console.log(err)
      }
  }
    loadQuote()
  // axios.get('https://api.kanye.rest/')
  //   .then( response => {
  //     // handle response
  //     quote.value = response.data.quote
  //   })
  const createPost = () =>{
  axios.post('https//jsonplaceholder.typicode.com/posts',
      JSON.stringify({
        title: 'foo',
        body: 'bar',
        userId: 1,
      })
  ) .then(response => {
    console.log(response)
  }) 
  }

    return{
      createPost,  
      quote
    }

  }
}
</script>

<style>
 
</style>
