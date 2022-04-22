<template>
  <p>
    <img
      v-if="hasImage"
      @error="imageError($event)"
      class="flag"
      :src="require(`@/assets/img/${flag}.png`)"
      :alt="flag"
    />
    <span v-else class="languageError">
      {{ flag }}
    </span>
  </p>
</template>

<script>
export default {
  name: "FlagComponent",
  props: {
    flag: String,
  },
  data() {
    return {
      hasError: false,
      disponibleFlags: [
        "ca",
        "da",
        "de",
        "en",
        "it",
        "es",
        "ja",
        "no",
        "nl",
        "pt",
        "ro",
        "ru",
        "zh",
        "fr",
        "sv",
      ],
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
      return this.disponibleFlags.includes(this.flag);
    },
  },
};
</script>

<style scoped lang="scss">
.flag {
  width: 20px;
}
</style>