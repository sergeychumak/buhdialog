<template>
  <div id="app">
    <Header />
    <MainBanner />
    <Content />
    <Footer />
  </div>
</template>

<script>

import './assets/style/style.scss'

import Header from './components/templates/Header.vue'
import MainBanner from './components/templates/MainBanner.vue'
import Content from './components/templates/Content.vue'
import Footer from './components/templates/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    MainBanner,
    Content,
    Footer
  }
}
</script>

<style></style>
