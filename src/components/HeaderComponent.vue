<template>
  <div class="container">
    <div class="logoImg">
      <img src="@/assets/logo.png" alt="Logo" />
    </div>
    <div class="inputSearch">
      <input
        type="text"
        v-model="ricercaUtente"
        @keyup.enter="$emit('ricerca', ricercaUtente)"
      />
      <button @click="$emit('ricerca', ricercaUtente)">Search</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderComponent",
  data() {
    return {
      ricercaUtente: "",
    };
  },
};
</script>


<style lang="scss" scope>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  align-items: center;
  background-color: black;
  padding: 15px 0;

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