<template>
  <div>
    <h3>{{ film.title }}</h3>
    <h4>{{ film.original_title }}</h4>
    <p>
      <img
        v-if="hasImage"
        @error="imageError($event)"
        class="flag"
        :src="require(`@/assets/img/${film.original_language}.png`)"
        :alt="film.original_language"
      />
      <span v-else class="languageError">
        {{ film.original_language }}
      </span>
    </p>
    <p>{{ "vote: " + film.vote_average }}</p>
  </div>
</template>

<script>
export default {
  name: "FilmItem",
  props: {
    film: Object,
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
      return this.disponibleFlags.includes(this.film.original_language);
    },
  },
};
</script>

<style lang="scss" scoped>
.flag {
  width: 20px;
}
</style>