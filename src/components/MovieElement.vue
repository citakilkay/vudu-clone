<template>
  <div class="card">
    <h3 class="card__header">SALE</h3>
    <div class="card__body" @mouseover="addActive" @mouseleave="removeActive" :style="{ backgroundImage: 'url'+'('+`https://image.tmdb.org/t/p/original/${movie.poster_path}`+ ')' }">
      <h3 class="card__title">
        {{ movie.original_title }}
      </h3>
      <div class="card__date">
        {{ movie.release_date.substring(0, 4) }}
        <span class="card__badge">90min</span>
      </div>
      <div class="card__rating">
        <span class="fas fa-star"></span>
        <span class="fas fa-star"></span>
        <span class="fas fa-star"></span>
        <span class="fas fa-star"></span>
        <span class="fas fa-star"></span>
      </div>
      <div class="card__price">Rent/Buy from $2.99</div>
      <a class="card__adult">{{ movie.adult ? "+18" : "+12" }} </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["movie"],
  setup(props) {
    const addActive = (e) => {
      const cardTitle = e.target.querySelector('.card__title');
      const cardDate = e.target.querySelector('.card__date');
      const cardRating = e.target.querySelector('.card__rating');
      const cardPrice = e.target.querySelector('.card__price');
      const cardAdult = e.target.querySelector('.card__adult');
      cardTitle.classList.add('-active');
      cardDate.classList.add('-active');
      cardRating.classList.add('-active');
      cardPrice.classList.add('-active');
      cardAdult.classList.add('-active');
    }
    const removeActive = (e) => {
      const cardTitle = e.target.querySelector('.card__title');
      const cardDate = e.target.querySelector('.card__date');
      const cardRating = e.target.querySelector('.card__rating');
      const cardPrice = e.target.querySelector('.card__price');
      const cardAdult = e.target.querySelector('.card__adult');
      cardTitle.classList.remove('-active');
      cardDate.classList.remove('-active');
      cardRating.classList.remove('-active');
      cardPrice.classList.remove('-active');
      cardAdult.classList.remove('-active');
    }
    return {
        addActive,
        removeActive
    }
  },
};
</script>

<style lang="scss" scoped>
    @import '../assets/scss/movie-element.scss'
</style>