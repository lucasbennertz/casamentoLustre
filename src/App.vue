<template>
  <SiteHeader />
  <main>
    <FundoImagem />

    <section id="historia" class="content-section reveal">
      <div class="section-inner">
        <h2>Nossa história</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent luctus, nisl at vehicula facilisis, velit mauris posuere tortor, at viverra mauris ipsum a ante.
        </p>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse sed urna in justo euismod condimentum. Fusce placerat enim et odio molestie sagittis.
        </p>
      </div>
    </section>

    <section id="evento" class="content-section alt-bg reveal">
      <div class="section-inner split">
        <article class="card">
          <h2>Cerimônia</h2>
          <p><strong>Data:</strong> Lorem ipsum dolor sit amet.</p>
          <p><strong>Horário:</strong> Lorem ipsum dolor sit amet.</p>
          <p><strong>Local:</strong> Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </article>
        <article class="card">
          <h2>Recepção</h2>
          <p><strong>Data:</strong> Lorem ipsum dolor sit amet.</p>
          <p><strong>Horário:</strong> Lorem ipsum dolor sit amet.</p>
          <p><strong>Local:</strong> Lorem ipsum dolor sit amet, consectetur adipiscing elit.</p>
        </article>
      </div>
    </section>

    <section id="local" class="content-section reveal">
      <div class="section-inner">
        <h2>Localização</h2>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec feugiat lorem id velit posuere, vitae suscipit nibh placerat.</p>
        <p><strong>Endereço:</strong> Lorem ipsum dolor sit amet, 123 - Lorem, Ipsum</p>
        <div class="map-placeholder" role="img" aria-label="Mapa de localização do evento">
          Lorem ipsum - mapa do local
        </div>
      </div>
    </section>

    <section id="dress-code" class="content-section alt-bg reveal">
      <div class="section-inner">
        <h2>Dress code</h2>
        <p>
          Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris nec lorem at sem dapibus vulputate vitae vel augue.
        </p>
      </div>
    </section>

    <section id="faq" class="content-section reveal">
      <div class="section-inner">
        <h2>FAQ</h2>
        <details>
          <summary>Lorem ipsum dolor sit amet?</summary>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Integer posuere erat a ante.</p>
        </details>
        <details>
          <summary>Lorem ipsum consectetur adipiscing?</summary>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus sagittis lacus vel augue laoreet rutrum.</p>
        </details>
        <details>
          <summary>Lorem ipsum viverra mauris?</summary>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras mattis consectetur purus sit amet fermentum.</p>
        </details>
      </div>
    </section>

    <section id="rsvp" class="content-section alt-bg reveal">
      <div class="section-inner">
        <h2>RSVP</h2>
        <p>Lorem ipsum dolor sit amet, confirme sua presença preenchendo os campos abaixo.</p>
        <form class="rsvp-form" @submit.prevent>
          <label for="nome">Nome completo</label>
          <input id="nome" type="text" placeholder="Lorem ipsum" />

          <label for="presenca">Presença</label>
          <select id="presenca">
            <option>Sim, lorem ipsum</option>
            <option>Não poderei comparecer</option>
          </select>

          <label for="acompanhantes">Acompanhantes</label>
          <input id="acompanhantes" type="number" min="0" placeholder="0" />

          <label for="observacoes">Restrições / observações</label>
          <textarea id="observacoes" rows="4" placeholder="Lorem ipsum dolor sit amet"></textarea>

          <button type="submit">Enviar confirmação</button>
        </form>
      </div>
    </section>
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
  --text-color: #1f2937;
  --surface: #f7f5f2;
  --surface-alt: #ece8e1;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: var(--primary-font);
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: var(--surface);
  color: var(--text-color);
  overflow-x: hidden;
  line-height: 1.6;
}

h1, h2, h3 {
  font-family: var(--title-font);
}

main {
  display: block;
}

.content-section {
  padding: clamp(3rem, 8vw, 5.5rem) 1rem;
}

.alt-bg {
  background-color: var(--surface-alt);
}

.section-inner {
  width: min(1000px, 100%);
  margin: 0 auto;
}

.section-inner h2 {
  margin-bottom: 0.8rem;
  font-size: clamp(1.7rem, 4vw, 2.6rem);
}

.section-inner p + p {
  margin-top: 0.7rem;
}

.split {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1rem;
}

.card {
  background: #fff;
  border-radius: 1rem;
  padding: 1.1rem;
  border: 1px solid #e5e7eb;
}

.map-placeholder {
  margin-top: 1rem;
  min-height: 280px;
  border-radius: 1rem;
  display: grid;
  place-items: center;
  background: linear-gradient(135deg, #d4d4d8, #e5e7eb);
  color: #374151;
  font-weight: 500;
}

details {
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 0.8rem;
  padding: 0.8rem 0.9rem;
}

details + details {
  margin-top: 0.7rem;
}

summary {
  cursor: pointer;
  font-weight: 600;
}

.rsvp-form {
  margin-top: 1rem;
  display: grid;
  gap: 0.55rem;
}

.rsvp-form input,
.rsvp-form select,
.rsvp-form textarea {
  width: 100%;
  padding: 0.72rem 0.8rem;
  border-radius: 0.6rem;
  border: 1px solid #d1d5db;
  font: inherit;
}

.rsvp-form button {
  width: fit-content;
  border: 0;
  border-radius: 999px;
  padding: 0.7rem 1rem;
  background: #1f2937;
  color: #fff;
  font: inherit;
  cursor: pointer;
}

.reveal {
  animation: fade-up 0.5s ease;
}

@keyframes fade-up {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@media (max-width: 780px) {
  .split {
    grid-template-columns: 1fr;
  }
}
</style>
