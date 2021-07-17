<template>
<div class="list">
    <div class="list__header">
        <a class="list__title">Hot Release</a>
        <a class="list__view-all">View All</a>
    </div>
    <div class="list__body">
        <div class="list__item" v-for="movie in movieList" v-bind:key="movie.id">
            <MovieElement :movie="movie"/>
        </div>
    </div>
</div>
  
</template>

<script>
import MovieElement from './MovieElement.vue';
export default {
    components: {
        MovieElement
    },
    props:['movieList'],
    setup() {

    }
}
</script>

<style lang='scss' scoped>
    @import '../assets/scss/movielist.scss';
</style>