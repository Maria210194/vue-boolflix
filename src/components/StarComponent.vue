<template>
  <div class="star">
    <p>Vote: {{ voteCalculator }}</p>
    <i
      v-for="index in voteCalculator"
      :key="index"
      class="fa-solid fa-star"
    ></i>
  </div>
</template>

<script>
export default {
  name: "StarComponent",
  props: {
    corectVote: Number,
    item: Object,
  },
  computed: {
    voteCalculator() {
      const vote = Math.round(this.corectVote / 2);
      return vote;
    },
  },
};
</script>

<style scoped lang='scss'>
.star {
  display: flex;

  i {
    color: orange;
  }
}
</style>