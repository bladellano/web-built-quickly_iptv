<template>
  <section class="section bg-gradient-to-br from-primary to-purple-600 py-20">
    <div class="section-container">
      <div class="max-w-4xl mx-auto text-center">
        <div class="inline-block mb-6 px-6 py-3 bg-white/20 backdrop-blur-sm rounded-full animate-pulse-slow">
          <span class="text-2xl font-bold">⏰ OFERTA EXCLUSIVA</span>
        </div>

        <h2 class="text-4xl md:text-5xl font-bold mb-6 text-white">
          Assine hoje e ganhe <span class="text-yellow-300">1 MÊS GRÁTIS</span>!
        </h2>

        <p class="text-xl text-white/90 mb-8 max-w-2xl mx-auto">
          Promoção válida apenas para os primeiros 100 assinantes. 
          Não perca essa oportunidade única!
        </p>

        <!-- Countdown Timer -->
        <div class="flex justify-center gap-4 mb-8">
          <div v-for="(unit, index) in countdown" :key="index" class="countdown-unit">
            <div class="countdown-value">{{ unit.value }}</div>
            <div class="countdown-label">{{ unit.label }}</div>
          </div>
        </div>

        <!-- CTA Buttons -->
        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
          <a href="#assinar" class="btn-white text-lg">
            🎁 Garantir Meu Desconto
          </a>
          <div class="text-white/80 text-sm">
            ✅ Sem compromisso • Cancele quando quiser
          </div>
        </div>

        <!-- Social Proof -->
        <div class="mt-12 flex items-center justify-center gap-8 flex-wrap">
          <div class="flex items-center gap-2">
            <div class="flex -space-x-2">
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-blue-400 to-blue-600 border-2 border-white"></div>
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-green-400 to-green-600 border-2 border-white"></div>
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-purple-400 to-purple-600 border-2 border-white"></div>
              <div class="w-10 h-10 rounded-full bg-gradient-to-br from-pink-400 to-pink-600 border-2 border-white"></div>
            </div>
            <div class="text-left text-white">
              <div class="font-bold">2.500+</div>
              <div class="text-sm opacity-80">Clientes Satisfeitos</div>
            </div>
          </div>

          <div class="flex items-center gap-2">
            <div class="text-yellow-400 text-2xl">⭐⭐⭐⭐⭐</div>
            <div class="text-white font-semibold">4.9/5</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const countdown = ref([
  { value: '23', label: 'Horas' },
  { value: '45', label: 'Minutos' },
  { value: '12', label: 'Segundos' }
])

let intervalId = null

onMounted(() => {
  // Simula um countdown (você pode implementar lógica real aqui)
  intervalId = setInterval(() => {
    let seconds = parseInt(countdown.value[2].value)
    let minutes = parseInt(countdown.value[1].value)
    let hours = parseInt(countdown.value[0].value)

    if (seconds > 0) {
      seconds--
    } else {
      seconds = 59
      if (minutes > 0) {
        minutes--
      } else {
        minutes = 59
        if (hours > 0) {
          hours--
        } else {
          hours = 23
        }
      }
    }

    countdown.value[0].value = String(hours).padStart(2, '0')
    countdown.value[1].value = String(minutes).padStart(2, '0')
    countdown.value[2].value = String(seconds).padStart(2, '0')
  }, 1000)
})

onUnmounted(() => {
  if (intervalId) {
    clearInterval(intervalId)
  }
})
</script>

<style scoped>
.countdown-unit {
  background: rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
  border-radius: 1rem;
  padding: 1.5rem;
  min-width: 100px;
  border: 2px solid rgba(255, 255, 255, 0.3);
}

.countdown-value {
  font-size: 3rem;
  font-weight: 800;
  color: white;
  line-height: 1;
}

.countdown-label {
  font-size: 0.875rem;
  color: rgba(255, 255, 255, 0.9);
  margin-top: 0.5rem;
  font-weight: 600;
}

.btn-white {
  background: white;
  color: #6366f1;
  padding: 1rem 2rem;
  border-radius: 0.75rem;
  font-weight: 700;
  text-decoration: none;
  display: inline-block;
  transition: all 0.3s ease;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
}

.btn-white:hover {
  transform: translateY(-2px);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
}

@media (max-width: 640px) {
  .countdown-unit {
    min-width: 80px;
    padding: 1rem;
  }

  .countdown-value {
    font-size: 2rem;
  }
}
</style>
