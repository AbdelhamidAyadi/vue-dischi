<template>
  <div class="body">
    <header>
   <HeaderComp  @selectionGenre="selectionGenre" @selectionArtist="selectionArtist"/>
    </header>
    <main>
      <MainComp :resultArtist="resultArtist" :resultGenre="resultGenre"/>
    </main>
  </div>
</template>

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'
export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  },
  data(){
    return{
      resultGenre:"",
      resultArtist:""
    }

  },
  methods:{
    selectionGenre(text){
      this.resultGenre = text
    },
    selectionArtist(text){
      this.resultArtist = text
    }
  }
}
</script>

<style lang="scss">
@import "bootstrap/dist/css/bootstrap.min.css";

 
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.body{
  background-color: #1e2d3b;
  min-height: 100vh;
  position: relative;
}

</style>
