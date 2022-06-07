<template>
    <div class="album-card">
        <img :src="album.poster" :alt="album.title">
        <h3>{{album.title}}</h3>
        <h5>{{album.author}}</h5>
        <h5>{{album.year}}</h5>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',

    props: {
        album: Object,
    }
}
</script>

<style lang="scss" scoped>
.album-card {
    background-color: var(--primary-color);
    padding: 1rem;
    text-align: center;
    text-transform: uppercase;

    img {
        max-width: 100%;
    }

    h3 {
        padding: 0.5rem 0;
        color: var(--tertiary-color);
    }

    h5 {
        color:lightgray;
    }
}
</style>