<template>
    <form class="form-group" @change="$emit('selected', genreSelected)">
        <label for="select"><h4>Choose a genre:</h4></label>
        <select class="form-control" name="select" id="select" v-model="genreSelected">
            <option value="" disabled selected></option>
            <option value="Rock">Rock</option>
            <option value="Pop">Pop</option>
            <option value="Jazz">Jazz</option>
            <option value="Metal">Metal</option>
            <option value="All">All genres</option>
        </select>
    </form>
</template>

<script>
export default {
    name: 'GenreSelect',

    data() {
        return {
            genreSelected: "",
        }
    }
}
</script>

<style lang='scss' scoped>
h4 {
    color: var(--tertiary-color);
}

select {
    width: 25rem;
    margin-bottom: 1.875rem;
}


</style>