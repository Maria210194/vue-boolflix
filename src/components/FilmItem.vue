<template>
  <div class="">
    <img class="poster" :src="ricercaPoster(film.poster_path)" :alt="title" />
    <h3>{{ film.title }}</h3>
    <h4>{{ film.original_title }}</h4>
    <FlagComponent :flag="film.original_language" />
    <StarComponent :corectVote="film.vote_average" />
  </div>
</template>

<script>
import FlagComponent from "./FlagComponent.vue";
import StarComponent from "./StarComponent.vue";

export default {
  name: "FilmItem",
  props: {
    film: Object,
    poster: String,
    title: String,
  },
  components: {
    FlagComponent,
    StarComponent,
  },
  methods: {
    ricercaPoster: function (path) {
      if (path === null) {
        return "https://upload.wikimedia.org/wikipedia/commons/thumb/6/65/No-Image-Placeholder.svg/330px-No-Image-Placeholder.svg.png";
      }
      return `https://image.tmdb.org/t/p/original${path}`;
    },
  },
};
</script>

<style lang="scss" scoped>
</style>