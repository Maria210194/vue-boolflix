<template>
  <div id="app">
    <HeaderComponent @ricerca="queryApi" />
    <MainComponent />
  </div>
</template>

<script>
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";
import axios from "axios";

export default {
  name: "App",
  components: {
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "4efb87d52a46e108a98dadb3dd2051f1",
      arraySerie: [],
      arrayFilm: [],
    };
  },
  methods: {
    queryApi(cerca) {
      if (cerca !== "") {
        const params = {
          query: cerca,
          api_key: this.apiKey,
          language: "it-IT",
        };

        // chiamata:
        axios
          .get(this.apiUrl + "tv", { params })
          .then((response) => {
            console.log(response.data.results);
            this.arraySerie = response.data.results;
            console.log(this.arraySerie);
          })
          .catch((error) => {
            console.log(error);
          });
      }
    },
  },
};
</script>

<style lang="scss">
#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
