<template>
  <div class="container">
    <FilmList :films="films" />
    <SeriesList :series="series" />
  </div>
</template>

<script>
import FilmList from "./FilmList.vue";
import SeriesList from "./SeriesList.vue";

export default {
  name: "MainComponent",
  props: {
    films: Array,
    series: Array,
  },
  components: {
    FilmList,
    SeriesList,
  },
};
</script>

<style lang="scss" scoped>
.container {
  min-height: 800px;
  background-color: black;
  color: white;
}
</style>