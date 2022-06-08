<template>
  <section class="albums">
    <div class="container">
      <GenreSelect class="genre-select"/>
      <div class="row row-cols-lg-5">
        <AlbumCard class="album-card col-12 col-sm-6 col-lg mb-5" v-for="(album, index) in albums" :key="index" :album="album"/>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import AlbumCard from '../commons/AlbumCard.vue';
import GenreSelect from '../commons/GenreSelect.vue';

export default {
  name: 'AlbumsSection',

  components: {
    AlbumCard,
    GenreSelect,
  },

  data() {
    return {
      albums: [],
    }
  },

  created() {
    // Make a request for a user with a given ID
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
      // handle success
      this.albums = response.data.response;
      console.log(this.albums);
    })
    .catch((error) => {
      // handle error
      console.log(error);
    })
    .then(() => {
      // always executed
    });
  },
}
</script>

<style lang="scss" scoped>

</style>