<template>
  <div id="app">
    <div class="container">
      <Navigation />
      <News />
      <Article />
      <Team />
      <Footer />
    </div>
  </div>
</template>

<script>
import Navigation from "./components/Navigation.vue"
import News from "./components/News.vue"
import Article from "./components/Article.vue"
import Team from "./components/Team.vue"
import Footer from './components/Footer.vue'

export default {
  name: "App",
  components: {
    Navigation,
    News,
    Article,
    Team,
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
