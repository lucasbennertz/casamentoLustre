<template>
  <section class="timer-card" aria-label="Contagem regressiva para o casamento">
    <h2 class="timer-title">Faltam:</h2>

    <p v-if="isExpired" class="timer-message">Chegou o grande dia!</p>

    <div v-else class="timer-grid" role="timer" aria-live="polite">
      <article class="timer-unit">
        <span class="timer-value">{{ formatNumber(timeLeft.months) }}</span>
        <span class="timer-label">Meses</span>
      </article>
      <article class="timer-unit">
        <span class="timer-value">{{ formatNumber(timeLeft.days) }}</span>
        <span class="timer-label">Dias</span>
      </article>
      <article class="timer-unit timer-inline">
        <span class="timer-value">{{ formatNumber(timeLeft.hours) }}</span>
        <span class="timer-separator">:</span>
        <span class="timer-value">{{ formatNumber(timeLeft.minutes) }}</span>
        <span class="timer-separator">:</span>
        <span class="timer-value">{{ formatNumber(timeLeft.seconds) }}</span>
        <span class="timer-label timer-label-inline">Horas : Min : Seg</span>
      </article>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onUnmounted, ref } from 'vue'

const targetDate = new Date('2026-10-17T09:30:00').getTime()

const timeLeft = ref({
  months: 0,
  days: 0,
  hours: 0,
  minutes: 0,
  seconds: 0
})

const isExpired = ref(false)
let intervalId = null

const formatNumber = (value) => String(value).padStart(2, '0')

const updateCountdown = () => {
  const now = Date.now()
  const distance = targetDate - now

  if (distance <= 0) {
    isExpired.value = true
    timeLeft.value = {
      months: 0,
      days: 0,
      hours: 0,
      minutes: 0,
      seconds: 0
    }

    if (intervalId) {
      clearInterval(intervalId)
      intervalId = null
    }
    return
  }

  const monthMs = 1000 * 60 * 60 * 24 * 30.44
  const dayMs = 1000 * 60 * 60 * 24
  const hourMs = 1000 * 60 * 60
  const minuteMs = 1000 * 60

  timeLeft.value = {
    months: Math.floor(distance / monthMs),
    days: Math.floor((distance % monthMs) / dayMs),
    hours: Math.floor((distance % dayMs) / hourMs),
    minutes: Math.floor((distance % hourMs) / minuteMs),
    seconds: Math.floor((distance % minuteMs) / 1000)
  }
}

onMounted(() => {
  updateCountdown()
  intervalId = setInterval(updateCountdown, 1000)
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>

<style scoped>
.timer-card {
  width: min(900px, 90%);
  margin: 0 auto;
  padding: clamp(1.25rem, 3vw, 2rem);
  border-radius: 1.25rem;
  background: rgba(255, 255, 255, 0.2);
  border: 1px solid rgba(255, 255, 255, 0.4);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  color: #fff;
  box-shadow: 0 20px 35px rgba(0, 0, 0, 0.2);
}

.timer-title {
  margin: 0 0 1rem;
  font-size: clamp(1.6rem, 4vw, 2.25rem);
  text-align: center;
  text-shadow: 0 2px 12px rgba(0, 0, 0, 0.35);
}

.timer-grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(120px, 1fr));
  gap: clamp(0.6rem, 2vw, 1rem);
}

.timer-unit {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  min-height: 110px;
  padding: 0.75rem;
  border-radius: 0.9rem;
  background: rgba(18, 18, 18, 0.42);
}

.timer-value {
  font-size: clamp(1.5rem, 3.4vw, 2.4rem);
  line-height: 1;
  font-weight: 600;
}

.timer-label {
  margin-top: 0.35rem;
  font-size: clamp(0.72rem, 1.8vw, 0.95rem);
  text-transform: uppercase;
  letter-spacing: 0.08em;
}

.timer-inline {
  flex-direction: row;
  gap: 0.35rem;
  flex-wrap: wrap;
}

.timer-separator {
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  font-weight: 600;
}

.timer-label-inline {
  width: 100%;
  text-align: center;
}

.timer-message {
  text-align: center;
  font-size: clamp(1.2rem, 3vw, 1.8rem);
  padding: 0.9rem 0;
}

@media (max-width: 720px) {
  .timer-grid {
    grid-template-columns: 1fr;
  }
}
</style>
