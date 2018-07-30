<template>
  <div class="movie">
    <div class="movie-col-left">
      <img v-bind:src="movie.Poster" alt="">
    </div>
    <div class="movie-col-right">
      <div class="movie-title">
        <h2>{{ movie.Title }}</h2>
        <span class="movie-rating">{{ movie.Rated }}</span>
      </div>
      <div class="movie-sessions">
        <movie-session v-for="session in filteredSessions(sessions)" v-bind:key="session.id" v-bind:session="session" class="session-time-wrapper"></movie-session>
      </div>
    </div>
  </div>
</template>
<script>
import MovieSession from './MovieSession.vue';

export default {
  props: ['movie', 'sessions', 'day'],
  components: {
    MovieSession
  },
  methods: {
    filteredSessions(sessions) {
      return sessions.filter( (session) => {
        return this.$moment(session.time).isSame(this.day, 'day');
      });
    }

  }
}
</script>
