<template>
  <section id="inicio" class="hero">
    <div class="hero-overlay">
      <div class="hero-content">
        <p class="eyebrow">Save the Date</p>
        <h1 class="hero-title">Lucas &amp; Ester</h1>
        <p class="hero-subtitle">
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus luctus urna sed urna ultricies ac tempor dui sagittis.
        </p>
        <HeroTimer />
      </div>
    </div>
  </section>
</template>

<script setup>
import HeroTimer from './temporizador/HeroTimer.vue'
</script>

<style scoped>
.hero {
  min-height: 100svh;
  width: 100%;
  background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0.08), rgba(0, 0, 0, 0.6)),
    url('../../assets/foto_pre-weeding.webp');
  background-size: cover;
  background-position: center 35%;
}

.hero-overlay {
  min-height: 100svh;
  display: grid;
  place-items: center;
  padding: clamp(6rem, 12vw, 8rem) 1rem 2rem;
}

.hero-content {
  width: min(1000px, 95%);
  text-align: center;
  color: #fff;
  animation: fade-up 0.7s ease;
}

.eyebrow {
  margin: 0 0 0.8rem;
  letter-spacing: 0.1em;
  text-transform: uppercase;
  font-size: clamp(0.82rem, 1.8vw, 1rem);
}

.hero-title {
  margin: 0;
  font-size: clamp(2.3rem, 8vw, 4.9rem);
  text-shadow: 0 10px 20px rgba(0, 0, 0, 0.35);
}

.hero-subtitle {
  width: min(680px, 100%);
  margin: 0.85rem auto 1.8rem;
  font-size: clamp(1rem, 2.5vw, 1.3rem);
  line-height: 1.55;
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(14px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 600px) {
  .hero-overlay {
    padding-top: 6.5rem;
  }
}
</style>
