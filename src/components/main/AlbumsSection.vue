<template>
  <section class="albums">
    <div class="container">
      <GenreSelect class="genre-select" @selected="filterGenres"/>
      <div class="row row-cols-lg-5 d-flex justify-content-center">
        <div class="album-card col-12 col-sm-6 col-lg mb-5" v-for="(album, index) in albumsFiltered" :key="index">
          <AlbumCard :album="album"/>
        </div>
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
      // albumsFiltered: [],
      genreSelected: "",
    }
  },

  created() {
    // Make a request for a user with a given ID
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
      // handle success
      this.albums = response.data.response;
      // this.albumsFiltered = response.data.response;
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

  methods: {
    filterGenres(genreSelected) {
      console.log(genreSelected);
      this.genreSelected = genreSelected;
      // if (genreSelected == "All") {
      //   this.albumsFiltered = this.albums;
      // } else {
      //   this.albumsFiltered = this.albums.filter((album) => album.genre == genreSelected);
      // }
    }
  },

  computed: {
    albumsFiltered() {
      if (this.genreSelected == "All" || this.genreSelected == "") {
        return this.albums;
      } else {
        return this.albums.filter((album) => album.genre == this.genreSelected);
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.album-card {
  height: 28.125rem;
}
</style>