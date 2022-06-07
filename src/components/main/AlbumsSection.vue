<template>
  <section class="albums">
    <div class="container">
      <div class="row">
      </div>
    </div>
  </section>
</template>

<script>
import axios from 'axios';

export default {
  name: 'AlbumsSection',

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