<template>
  <div>
    <input type="text" v-model="query" />
    <button @click="queryApi">Search</button>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HeaderComponent",
  data() {
    return {
      apiUrl: "https://api.themoviedb.org/3/search/",
      apiKey: "4efb87d52a46e108a98dadb3dd2051f1",

      query: "",
    };
  },
  methods: {
    queryApi() {
      const params = {
        query: this.query,
        api_key: this.apiKey,
      };
      axios
        .get(this.apiUrl + "movie", { params })
        .then((response) => {
          console.log(response);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<style>
</style>