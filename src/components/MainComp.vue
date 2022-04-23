<template>
  <div>




    <div v-if="success" class="mega_container">
      <SongComp v-for="(element , index) in filteredList" :key="index" :poster="element.poster" :title="element.title"
        :author="element.author" :year="element.year" />
    </div>






    <div v-else class="loading">
      <div class="spinner-border" role="status">

      </div>
    </div>
  </div>
</template>

<script>
  import SongComp from '../components/SongComp.vue'
  import axios from 'axios'


  export default {
    name: 'MainComp',
    props: {
      resultGenre: String,
      resultArtist: String,
    },
    components: {
      SongComp,
    },
    data() {
      return {
        songs: [],
        success: false,
        artist: "",
        genre: "",
        filteredList: this.songs

      }
    },
    created() {
      const self = this;

      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then(function (response) {

          self.songs = response.data.response
          self.success = response.data.success
          self.filteredList = self.songs



        })

    },

    watch: {
      resultGenre: function () {

        this.genre = this.resultGenre

        if (this.genre == "All") {
          this.filteredList = this.songs
        } else {
          this.filteredList = this.songs.filter((elem) => {
              if (elem.genre == this.genre) {
                return true
              }
              return false
            }

          )
        }
      },
      resultArtist: function () {

        this.artist = this.resultArtist

        if (this.artist == "All") {
          this.filteredList = this.songs
        } else {
          this.filteredList = this.songs.filter((elem) => {
              if (elem.author == this.artist) {
                return true
              }
              return false
            }

          )
        }
      }
    },



  }
</script>

<style scoped lang="scss">
  .mega_container {
    display: flex;
    justify-content: center;
  
    flex-wrap: wrap;
    width: 60%;
    margin: 0 auto;
  }

  .loading {
    .spinner-border {
      width: 5rem;
      height: 5rem;
    }

    color: white;
    position: absolute;
    left: 50%;
    top: 50%;

  }
</style>