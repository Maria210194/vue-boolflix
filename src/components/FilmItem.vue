<template>
  <div>
    <h3>{{ film.title }}</h3>
    <h4>{{ film.original_title }}</h4>
    <FlagComponent :flag="film.original_language" />
    <p>{{ "vote: " + film.vote_average }}</p>
  </div>
</template>

<script>
import FlagComponent from "./FlagComponent.vue";

export default {
  name: "FilmItem",
  props: {
    film: Object,
  },
  components: {
    FlagComponent,
  },
};
</script>

<style lang="scss" scoped>
</style>