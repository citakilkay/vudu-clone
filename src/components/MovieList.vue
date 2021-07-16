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
    setup(props) {
        console.log(props.movieList)
    }
}
</script>

<style lang='scss' scoped>
    .list {
        font-family: 'Roboto', sans-serif;
        // Container
        margin: 0 auto;
        margin-top: 1.5rem;
        
        width: 87%;
        &__header {
            // flexbox
            display: flex;
            flex-direction: row;
            flex-wrap: nowrap;
            align-items: flex-start;
            justify-content: space-between;
            margin-bottom: 1rem;
        }
        &__title {
            font-size: 1.1rem;
            font-weight: bold;
            color: $item-text-color;
            cursor: pointer;
            &:hover {
                color: $navbar-item-hover;
                text-decoration: underline;
                text-decoration-color: $text-underline;
            }
        }
        &__view-all {
            cursor: pointer;
            font-size: 1rem;
            color: $view-all-color;

            &:hover {
                color: $item-text-color;
            }
        }
        &__body {
            display: flex;
            flex-direction: row;
            flex-wrap: nowrap;
            align-items: flex-start;
            justify-content: flex-start;
            overflow: hidden;
        }
    }
</style>