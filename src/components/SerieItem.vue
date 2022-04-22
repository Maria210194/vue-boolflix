<template>
  <div>
    <h3>{{ serie.name }}</h3>
    <h4>{{ serie.original_name }}</h4>
    <p>
      <img
        v-if="hasImage"
        @error="imageError($event)"
        class="flag"
        :src="require(`@/assets/img/${serie.original_language}.png`)"
        :alt="serie.original_language"
      />
      <span v-else class="languageError">
        {{ serie.original_language }}
      </span>
    </p>
    <p>{{ "vote: " + serie.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: "SerieItem",
  props: {
    serie: Object,
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