<template>
  <header>
    <div class="container">
        <img src="../../assets/img/spotify-logo.png" alt="Spotify-logo">
    </div>
  </header>
</template>

<script>
export default {
 name: 'BaseHeader',
}
</script>

<style lang="scss" scoped>
header {
    background-color: var(--primary-color);
    padding: 0.5rem 0;

    img{
        max-width: 3.75rem;
    }
}
</style>