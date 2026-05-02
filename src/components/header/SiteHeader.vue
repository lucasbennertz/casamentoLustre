<template>
  <header class="header">
    <div class="header-content">
      <a class="logo" href="#inicio" aria-label="Voltar para o início">Lucas &amp; Ester</a>
      <nav class="nav-links" aria-label="Navegação principal">
        <a href="#historia">História</a>
        <a href="#evento">Evento</a>
        <a href="#local">Local</a>
        <a href="#faq">FAQ</a>
      </nav>
      <a class="cta-button" href="#rsvp">Confirmar presença</a>
    </div>
  </header>
</template>

<script setup>
</script>

<style scoped>
.header {
  position: fixed;
  top: 1rem;
  left: 50%;
  transform: translateX(-50%);
  width: min(1200px, 95%);
  padding: 0.7rem 1rem;
  border-radius: 999px;
  background: rgba(18, 18, 18, 0.35);
  border: 1px solid rgba(255, 255, 255, 0.35);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  z-index: 100;
}

.header-content {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 0.8rem;
}

.logo {
  color: #fff;
  text-decoration: none;
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.1rem, 2.2vw, 1.55rem);
  white-space: nowrap;
}

.nav-links {
  display: flex;
  gap: 0.9rem;
  overflow-x: auto;
  padding-bottom: 0.2rem;
}

.nav-links a {
  color: #fff;
  text-decoration: none;
  font-size: 0.95rem;
  white-space: nowrap;
}

.cta-button {
  text-decoration: none;
  color: #1f2a37;
  background: #f5f5f4;
  border-radius: 999px;
  padding: 0.5rem 0.9rem;
  font-size: 0.88rem;
  white-space: nowrap;
}

@media (max-width: 600px) {
  .header {
    top: 0.75rem;
  }

  .cta-button {
    display: none;
  }

  .nav-links {
    gap: 0.7rem;
  }
}
</style>
