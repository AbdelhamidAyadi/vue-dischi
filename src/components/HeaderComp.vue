<template>
  <div class="container_costum">
    <img src=".././assets/spotify.png" alt="">
    <form action="">
      <select name="genre" v-on:change="$emit('selectionGenre', genre)" v-model="genre" id="genre">
        <option disabled value="">Select a genre</option>
        <option value="All">All Genres</option>
        <option value="Rock">Rock</option>
        <option value="Pop">Pop</option>
        <option value="Jazz">Jazz</option>
        <option value="Metal">Metal</option>
      </select>
      <select name="artist" v-on:change="$emit('selectionArtist', artist)" v-model="artist" id="artist">
        <option disabled value="">Select an artist</option>
        <option value="All">All Artists</option>
        <option value="Bon Jovi">Bon Jovi</option>
        <option value="Queen">Queen</option>
        <option value="Sting">Sting</option>
        <option value="Steve Gadd Band">Steve Gadd Band</option>
        <option value="Iron Maiden">Iron Maiden</option>
        <option value="Eric Clapton">Eric Clapton</option>
        <option value="Deep Purple">Deep Purple</option>
        <option value="Metallica">Metallica</option>
        <option value="Dave Weckl">Dave Weckl</option>
        <option value="Michael Jacjson">Michael Jacjson</option>
      </select>
     
    </form>
  </div>
</template>

<script>
  export default {
    name: 'HeaderComp',
    
    data(){
      return{
        genre:"",
        artist:"",
      }
    },
    

  }
</script>

<style scoped lang="scss">
  .container_costum {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 10px;
    background: #2e3a46;

    img {
      height: 50px;
    }
    select{
      margin:0 15px;
    }
  }
</style>