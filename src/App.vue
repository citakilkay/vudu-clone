<template>
    <NavbarComp/>
    <SliderHeader :slides="slides"></SliderHeader>
    <MovieList :movieList="popularMovies"/>
    <MovieList :movieList="topRatedMovies"/>
</template>

<script>
import SliderHeader from './components/SliderHeader.vue';
import NavbarComp from './components/Navbar.vue';
import MovieList from './components/MovieList.vue';
import axios from 'axios';
import { ref, reactive } from "vue";
export default {
  components: {
    NavbarComp,
    SliderHeader,
    MovieList
  },
  setup() {
    const popularMoviesAPI = "https://api.themoviedb.org/3/discover/movie?api_key=d82e803cf4d908f91877fc18f83b746d&sort_by=popularity.desc";
    const topRatedMoviesAPI = "https://api.themoviedb.org/3/movie/top_rated?api_key=d82e803cf4d908f91877fc18f83b746d";
    
    const popularMovies = reactive([])
    const topRatedMovies = reactive([])
    const slides = reactive([]) // Array for Header Slider of popular movies

    // Get Popular Movies with Axios
    const getPopularMovies = async () => {
      const response = await axios.get(popularMoviesAPI);
      const apiData = response.data;
      for(let i=0; i<7; i++) {
        slides.push(apiData.results[i].backdrop_path);
      }
      apiData.results.forEach(data => {
        popularMovies.push(data);
      });
    };
    getPopularMovies();
    const getTopRatedMovies = async() => {
      const response = await axios.get(topRatedMoviesAPI);
      const apiData = response.data;
      apiData.results.forEach(data => {
        topRatedMovies.push(data);
      })
      console.log(topRatedMovies)
    }
    getTopRatedMovies();
    return {
      popularMovies,
      slides
    };
  },
};
</script>
<style lang='scss'>
</style>
