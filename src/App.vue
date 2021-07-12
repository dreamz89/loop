<template>
  <div id="app">
    <div class="container">
      <Navigation />
      <img alt="Vue logo" src="./assets/logo.png" />
      <HelloWorld msg="Welcome to Your Vue.js App" />
      <Footer />
    </div>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Navigation from "./components/Navigation.vue";
import Footer from './components/Footer.vue'

export default {
  name: "App",
  components: {
    HelloWorld,
    Navigation,
    Footer,
  },
};
</script>

<style lang="scss">
#app {
  background-color: $off-white;
}

.container {
  background-color: $white;
  max-width: 1400px;
  margin: 0 auto;
}
</style>
