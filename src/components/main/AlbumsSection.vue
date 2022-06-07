<template>
  <section class="albums">
    <div class="container">
      <div class="row">
        <div class="col-12 col-sm-6 col-lg"><AlbumCard/></div>
        <div class="col-12 col-sm-6 col-lg"><AlbumCard/></div>
        <div class="col-12 col-sm-6 col-lg"><AlbumCard/></div>
        <div class="col-12 col-sm-6 col-lg"><AlbumCard/></div>
        <div class="col-12 col-sm-6 col-lg"><AlbumCard/></div>
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';
import AlbumCard from '../commons/AlbumCard.vue';

export default {
  name: 'AlbumsSection',

  components: {
    AlbumCard,
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
section.albums {
  padding: 0.5rem 0;
}
</style>