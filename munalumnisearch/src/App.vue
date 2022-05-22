<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Welcome to Your Vue.js App" /> -->
  <searchbar/>
  
</template>

<script>
import searchbar from "./components/searchbar.vue"
import HelloWorld from "./components/HelloWorld.vue";
import Searchbar from './components/searchbar.vue';

export default {
  name: "App",
  components: {
    HelloWorld,
    Searchbar,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: white;
  margin-top: 60px;
}
</style>
