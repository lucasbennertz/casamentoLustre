<template>
  <SiteHeader />
  <main>
    <FundoImagem />
  </main>
</template>

<script setup>
import SiteHeader from './components/header/SiteHeader.vue'
import FundoImagem from './components/FundoImagem/FundoImagem.vue'
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500&family=Playfair+Display:ital,wght@0,400..900;1,400..900&display=swap');

:root {
  --primary-font: 'Montserrat', sans-serif;
  --title-font: 'Playfair Display', serif;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: var(--primary-font);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f8f9fa;
  overflow-x: hidden;
}

h1, h2, h3 {
  font-family: var(--title-font);
}
</style>
