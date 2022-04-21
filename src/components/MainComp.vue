<template>
  <div class="mega_container">
  <SongComp v-for="(element , index) in songs" :key="index"
  :poster ="element.poster"
  :title="element.title"
  :author="element.author"
  :year="element.year"

  />
  </div>
</template>

<script>

import SongComp from '../components/SongComp.vue'
import axios from 'axios'



  export default {
    name: 'MainComp',
    components:{
      SongComp,
    },
    data(){
      return{
        songs: [],
        
      }
    },
    created(){
      const self = this;
      
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
           .then(function (response) {
             
             self.songs = response.data.response
            
                                
           })
           
    }

  }
</script>

<style scoped lang="scss">
  .mega_container {
    display: flex;
    flex-wrap: wrap;
    width: 60% ;
    margin: 0 auto;
  }
</style>