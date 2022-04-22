<template>
  <div class="container">
    <h2>Series</h2>
    <div class="row">
      <div class="card" v-for="serie in series" :key="serie.id">
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
</style>