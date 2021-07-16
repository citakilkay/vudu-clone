<template>
  <div class="card">
    <h3 class="card__header">SALE</h3>
    <div class="card__body" :style="{ backgroundImage: 'url'+'('+`https://image.tmdb.org/t/p/original/${movie.poster_path}`+ ')' }">
      <h3 class="card__title">
        {{ movie.original_title }}
      </h3>
      <div class="card__date">
        {{ movie.release_date.substring(0, 4) }}
        <span class="card__badge">90min</span>
      </div>
      <div class="card__rating">
        <span class="far fa-star"></span>
        <span class="far fa-star"></span>
        <span class="far fa-star"></span>
        <span class="far fa-star"></span>
        <span class="far fa-star"></span>
      </div>
      <div class="card__">{{}}</div>
      <a class="card__adult">{{ movie.adult ? "+18" : "+12" }} </a>
    </div>
  </div>
</template>

<script>
export default {
  props: ["movie"],
  setup(props) {
    console.log(props.movie);
    console.log("feadwa");
    return {
        
    }
  },
};
</script>

<style lang="scss" scoped>
    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        margin-left: 0.6rem;
        margin-right: 0.6rem;
        line-height: 10px;
        &__header {
            border-radius: 4px 4px 0 0;
            display: block;
            width: 100%;
            padding-top: 0.4rem;
            padding-bottom: 0.4rem;
            background-color: #cf7b00;
            line-height: 10px;
            font-size: 1rem;
            text-align: center;
        }
        &__body {
            color: $item-text-color;
            line-height: 1.6rem;
            width: 9rem;
            height: 15rem;
            background-size: auto 100%;
            box-shadow:inset 0 0 0 200px #0000007e;
        }
        &__title {
            margin-top: auto;
        }
    }
</style>