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
  created() {
    // Make a request for a user with a given ID
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
      // handle success
      console.log(response.data.response);
    })
    .catch((error) => {
      // handle error
      console.log(error);
    })
    .then(() => {
      // always executed
    });
  }
}
</script>

<style lang="scss" scoped>

</style>