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

<style lang="scss" scope>
.container {
  max-width: 1200px;

  h2 {
    padding: 10px;
  }
  .row {
    display: flex;
    flex-wrap: wrap;
    text-align: center;

    .card {
      width: 18%;
      padding: 0.5rem;
      margin: 5px;
      color: white;
      border: 1px solid red;
      border-radius: 5px;
    }
  }
}
</style>