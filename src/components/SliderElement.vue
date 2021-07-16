<template>
    <div class="slider__inner" v-show="visibleSlide===index">
        <img :src="`https://image.tmdb.org/t/p/original/${imgPath}`" alt="slider-image">
    </div>
    
    <div></div>
    
</template>

<script>
export default {
    props: ['imgPath', 'index', 'visibleSlide'],
    setup(props) {
        
    }
}
</script>

<style scoped>
    img {
        width: 100%;
        height: auto;
    }
</style>