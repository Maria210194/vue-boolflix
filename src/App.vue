<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
    <HeaderComponent />
    <MainComponent />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import HeaderComponent from "./components/HeaderComponent.vue";
import MainComponent from "./components/MainComponent.vue";

import axios from "axios";

export default {
  name: "App",
  components: {
    HelloWorld,
    HeaderComponent,
    MainComponent,
  },
  data() {
    return {
      apiUrl: "https://developers.themoviedb.org/3/search/",
      apiKey: "4efb87d52a46e108a98dadb3dd2051f1",
    };
  },
  mounted() {
    axios.get(this.apiUrl + "tv");
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
