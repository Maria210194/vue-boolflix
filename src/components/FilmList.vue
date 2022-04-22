<template>
  <div>
    <div class="container">
      <h2>Film</h2>
      <div class="row">
        <div class="card" v-for="film in films" :key="film.id">
          <FilmItem :film="film" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FilmItem from "./FilmItem.vue";

export default {
  name: "FilmList",
  props: {
    films: Array,
  },
  components: {
    FilmItem,
  },
};
</script>

<style lang="scss" scoped>
</style>