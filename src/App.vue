<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <Home msg="Handbook Vue" />
  <List v-bind:records="records" />
</template>

<script>
import Home from "./components/Home.vue";
import List from "./components/List.vue";

export default {
  name: "App",
  components: {
    Home,
    List,
  },
  data() {
    return {
      records: [],
    };
  },
  mounted() {
    fetch(`${process.env.VUE_APP_SERVER_BASE_URL}/mongo`)
      .then((res) => res.json())
      .then((R) => {
        if (R.data) {
          this.records = R.data;
        }
      })
      .then(() => {
        console.log(this.records);
      });
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
