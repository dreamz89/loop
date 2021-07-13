<template>
  <div id="app">
    <div class="container">
      <Navigation />
      <Footer />
    </div>
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue"
import Footer from './components/Footer.vue'

export default {
  name: "App",
  components: {
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
  max-width: $desktop;
  margin: 0 auto;
}
</style>
