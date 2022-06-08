<template>
  <main>
      <div class="container">
          <AlbumsSection/>
      </div>
  </main>
</template>

<script>
import AlbumsSection from './AlbumsSection.vue';

export default {
    name: 'BaseMain',
    components: {
        AlbumsSection
    }
}
</script>

<style lang="scss" scoped>
main {
    background-color: var(--secondary-color);
    padding: 2rem 0;
}
</style>