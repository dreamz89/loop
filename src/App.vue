<template>
  <div id="app">
    <div class="container">
      <Navigation />
      <img alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Welcome to Your Vue.js App" />
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Navigation from "./components/Navigation.vue";

export default {
  name: "App",
  components: {
    HelloWorld,
    Navigation,
  },
};
</script>

<style lang="scss">
#app {
  background-color: $off-white;
}

.container {
  max-width: 1400px;
  margin: 0 auto;
}
</style>
