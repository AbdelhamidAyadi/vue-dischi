<template>
  <div class="container">
    <img :src="poster" alt="">
    <h2>{{title}}</h2>
    <p>{{author}}</p>
    <p>{{year}}</p>
  </div>
</template>

<script>

  export default {
    name: 'SongComp',
    props:{
      poster: String,
      title: String,
      author: String,
      year: String,


    }
    

  }
</script>

<style scoped lang="scss">
  .container {
   display: inline-block;
   background-color:#2e3a46 ;
   width: calc( ( 100% / 5 ) - 20px);
   padding: 20px 10px ;
   margin: 30px 10px;
   text-align: center;
   img{
     width: 80%;
   }
   h2{
     color: white;
     text-transform: uppercase;
     font-size: medium;
     margin: 15px 0;
   }
   p{
     color: grey;
   }
  }
</style>