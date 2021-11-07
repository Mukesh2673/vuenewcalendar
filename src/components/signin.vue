<template>
<div>
     <form  @submit.prevent="login">
         <input type="text" name="author" placeholder="author" v-model="posts.author"><br>
         <input type="text" name="title" placeholder="title" v-model="posts.title"><br><br>
         <button type="submit">Post</button>
    </form>
</div>
</template>
<script>


export default {
name:"signin",
data(){
    return{
        posts:{
            title:'',
            author:''
        }
    }
},
methods:{
    login()
    {
      this.axios.post("http://localhost:3000/posts/",this.posts)
      .then((result)=>{
          console.log(result);
      });
    }
    }
}



    




</script>