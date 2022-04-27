<template>
  <div class="">
    <img class="poster" :src="ricercaPoster(serie.poster_path)" :alt="title" />
    <h3>{{ serie.name }}</h3>
    <h5>{{ serie.original_name }}</h5>
    <FlagComponent :flag="serie.original_language" />
    <StarComponent :corectVote="serie.vote_average" />
  </div>
</template>

<script>
import FlagComponent from "./FlagComponent.vue";
import StarComponent from "./StarComponent.vue";

export default {
  name: "SerieItem",
  props: {
    serie: Object,
    title: String,
  },
  components: {
    FlagComponent,
    StarComponent,
  },
  methods: {
    imageError(event) {
      console.log("errore!");
      event.target.style.display = "none";
      this.hasError = true;
    },
    ricercaPoster: function (path) {
      if (path === null) {
        return "https://upload.wikimedia.org/wikipedia/commons/thumb/6/65/No-Image-Placeholder.svg/330px-No-Image-Placeholder.svg.png";
      }
      return `https://image.tmdb.org/t/p/original${path}`;
    },
  },

  computed: {
    hasImage() {
      return this.disponibleFlags.includes(this.serie.original_language);
    },
  },
};
</script>

<style lang="scss" scoped>
.flag {
  width: 20px;
}

.poster {
  width: 100px;
  height: 150px;
  transition: opacity 0.2s ease-in;
}

.card:hover .poster {
  opacity: 15%;
}
</style>