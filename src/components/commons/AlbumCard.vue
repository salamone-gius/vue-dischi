<template>
    <div class="album-card">
        <img src="https://via.placeholder.com/350" alt="">
        <h3>AlbumName</h3>
        <h5>Artist</h5>
        <h5>Year</h5>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
}
</script>

<style lang="scss" scoped>
.album-card {
    background-color: var(--primary-color);
    padding: 0.5rem;
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