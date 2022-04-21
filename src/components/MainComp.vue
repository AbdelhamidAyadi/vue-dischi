<template>
  <div>
    <div v-if="success" class="mega_container">
      <SongComp v-for="(element , index) in songs" :key="index" :poster="element.poster" :title="element.title"
        :author="element.author" :year="element.year" />
    </div>
    <div v-else class="loading">
      <div class="spinner-border" role="status">
        <span class="visually-hidden">Loading...</span>
      </div>
    </div>
  </div>
</template>

<script>
  import SongComp from '../components/SongComp.vue'
  import axios from 'axios'


  export default {
    name: 'MainComp',
    components: {
      SongComp,
    },
    data() {
      return {
        songs: [],
        success: false,

      }
    },
    created() {
      const self = this;

      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(function (response) {

          self.songs = response.data.response
          self.success = response.data.success

          console.log(self.success)

        })

    }

  }
</script>

<style scoped lang="scss">
  .mega_container {
    display: flex;
    flex-wrap: wrap;
    width: 60%;
    margin: 0 auto;
  }
  .loading{
    .spinner-border{
      width: 5rem;
      height: 5rem;
    }
    
    color: white;
    position: absolute;
    left: 50%;
    top: 50%;
    
  }
</style>