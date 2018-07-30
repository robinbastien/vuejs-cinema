<template>
  <div class="movie">
    <div class="movie-col-left">
      <img v-bind:src="movie.Poster" alt="">
    </div>
    <div class="movie-col-right">{{ movie.Title }}</div>
    <span class="movie-rating">{{ movie.Rated }}</span>
  </div>
</template>
<script>
export default {
  props: ['movie']
}
</script>
