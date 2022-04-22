<template>
  <div class="container">
    <h2>Series</h2>
    <div class="row">
      <div class="card" v-for="serie in series" :key="serie.name">
        <SerieItem :serie="serie" />
      </div>
    </div>
  </div>
</template>

<script>
import SerieItem from "./SerieItem.vue";

export default {
  name: "SeriesList",
  props: {
    series: Array,
  },
  components: {
    SerieItem,
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
    margin: 0 auto;

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