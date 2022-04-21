<template>
  <div class="container">
    <div class="logoImg">
      <img src="@/assets/logo.png" alt="Logo" />
    </div>
    <div class="inputSearch">
      <input
        type="text"
        placeholder="Ricerca per titolo"
        v-model="textToSearch"
      />
      <button @click="search">Search</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      textToSearch: "",
    };
  },
  methods: {
    search() {
      this.$emit("search", this.textToSearch);
    },
  },
};
</script>


<style lang="scss" scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  padding: 15px 0;
  background-color: black;
  color: white;

  .logoImg {
    width: 220px;
    img {
      width: 100%;
    }
  }
  .inputSearch {
    padding: 5px;
    input {
      padding: 5px 10px;
      background-color: white;
    }
    button {
      margin-left: 5px;
      padding: 5px;
      border-radius: 5px;
      background-color: red;
      color: white;
    }
  }
}
</style>