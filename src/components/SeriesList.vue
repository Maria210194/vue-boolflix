<template>
  <div class="container">
    <h2>Series</h2>
    <div class="row">
      <div class="card" v-for="serie in series" :key="serie.name">
        <h3>{{ serie.name }}</h3>
        <h4>{{ serie.original_name }}</h4>
        <p>{{ serie.original_language }}</p>
        <p>{{ "vote: " + serie.vote_average }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "SeriesList",
  props: {
    series: Array,
  },
};
</script>

<style lang="scss" scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
  h2 {
    padding: 10px;
  }
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