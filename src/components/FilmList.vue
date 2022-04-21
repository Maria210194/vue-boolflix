<template>
  <div>
    <div class="container">
      <h2>Film</h2>
      <div class="row">
        <div class="card" v-for="film in films" :key="film.id">
          <h3>{{ film.title }}</h3>
          <h4>{{ film.original_title }}</h4>
          <p>{{ film.original_language }}</p>
          <p>{{ film.vote_average }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FilmList",
  props: {
    films: Array,
  },
};
</script>

<style lang="scss" scope>
.container {
  max-width: 1200px;
  margin: 0 auto;
  .row {
    display: flex;
    flex-wrap: wrap;
    text-align: center;

    .card {
      width: 20%;
      padding: 0.5rem;
      color: white;
      border: 1px solid red;
    }
  }
}
</style>