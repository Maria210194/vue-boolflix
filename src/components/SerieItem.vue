<template>
  <div>
    <h3>{{ serie.name }}</h3>
    <h4>{{ serie.original_name }}</h4>
    <FlagComponent :flag="serie.original_language" />
    <p>{{ "vote: " + serie.vote_average }}</p>
  </div>
</template>

<script>
import FlagComponent from "./FlagComponent.vue";
export default {
  name: "SerieItem",
  props: {
    serie: Object,
  },
  components: {
    FlagComponent,
  },
  data() {
    return {
      hasError: false,
      disponibleFlags: ["en", "it", "es", "ru", "zh", "fr"],
    };
  },

  methods: {
    imageError(event) {
      console.log("errore!");
      event.target.style.display = "none";
      this.hasError = true;
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
</style>