<template>
  <div class="slider">
    <a class="slider__prev" @click="prevSlider">&#10094;</a>
    <div class="slider__body">
      <div class="slider__item" v-for="(slide, index) in slides" v-bind:key="slide">
      <SliderElement :imgPath="slide" v-bind:index="index" :visibleSlide="visibleSlide"></SliderElement>
      </div>
    </div>
    <a class="slider__next" @click="nextSlider">&#10095;</a>
    
  </div>
</template>

<script>
import SliderElement from './SliderElement.vue'
import { ref } from 'vue';
export default {
  props: ['slides'],
  components : {
    SliderElement
  },
  setup(props) {
    let visibleSlide = ref(0);
    const nextSlider = () => {
      if(props.slides.length-1 > visibleSlide.value) {
        visibleSlide.value++;
      }
    }
    const prevSlider = () => {
      if(visibleSlide.value > 0) {
        visibleSlide.value--;
      }
    }
    return {
      nextSlider,
      prevSlider,
      visibleSlide
    };
  },
};
</script>

<style lang='scss' scoped>
@import "../assets/scss/slider.scss";
</style>