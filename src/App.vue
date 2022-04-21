<template>
  <div id="app">
    <HeaderComponent @search="queryApi" />
    <MainComponent :films="arrayFilm" :series="arraySerie" />
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
    queryApi(textToSearch) {
      const params = {
        query: textToSearch,
        api_key: this.apiKey,
        language: "it-IT",
      };

      // chiamate per serie e film:
      axios
        .get(this.apiUrl + "tv", { params })
        .then((response) => {
          //console.log(response.data.results);
          if (response.status === 200) {
            this.arraySerie = response.data.results;
            console.log(this.arraySerie);
          }
        })
        .catch((error) => {
          console.log(error);
        });

      axios
        .get(this.apiUrl + "movie", { params })
        .then((response) => {
          console.log(response);
          if (response.status === 200) {
            this.arrayFilm = response.data.results;
          }
          //console.log(this.arrayFilm);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style lang="scss">
@import "@/assets/style/generals";
</style>
