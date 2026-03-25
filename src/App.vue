<script setup>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import Features from './components/Features.vue'
import Gallery from './components/Gallery.vue'
import Rules from './components/Rules.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div id="app">
    <Header />
    <main>
      <Hero />
      <Features />
      <Gallery />
      <Rules />
    </main>
    <Footer />
  </div>
</template>
<!--本网站由九条诗织@651715794个人独自完成,未经授权禁止盗用-->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, sans-serif;
  overflow-x: hidden;
}

#app {
  min-height: 100vh;
}
</style>
