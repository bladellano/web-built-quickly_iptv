<template>
  <section class="py-16 md:py-24 relative overflow-hidden">
    <!-- Background com efeito de urgência -->
    <div class="absolute inset-0 bg-gradient-to-r from-primary-900/50 via-accent-900/50 to-primary-900/50">
      <div class="absolute inset-0 bg-dark-950/80"></div>
    </div>
    
    <!-- Efeitos de luz pulsante -->
    <div class="absolute top-1/2 left-1/4 w-64 h-64 bg-primary-500/30 rounded-full filter blur-3xl animate-pulse"></div>
    <div class="absolute top-1/2 right-1/4 w-64 h-64 bg-accent-500/30 rounded-full filter blur-3xl animate-pulse" style="animation-delay: 1s;"></div>

    <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8 text-center">
      <!-- Ícone de oferta -->
      <div class="inline-flex items-center justify-center w-20 h-20 bg-gradient-to-br from-primary-500 to-accent-500 rounded-full mb-8 animate-pulse">
        <svg class="w-10 h-10 text-white" fill="currentColor" viewBox="0 0 24 24">
          <path d="M21.41 11.58l-9-9C12.05 2.22 11.55 2 11 2H4c-1.1 0-2 .9-2 2v7c0 .55.22 1.05.59 1.42l9 9c.36.36.86.58 1.41.58.55 0 1.05-.22 1.41-.59l7-7c.37-.36.59-.86.59-1.41 0-.55-.23-1.06-.59-1.42zM5.5 7C4.67 7 4 6.33 4 5.5S4.67 4 5.5 4 7 4.67 7 5.5 6.33 7 5.5 7z"/>
        </svg>
      </div>

      <!-- Título da oferta -->
      <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
        🔥 Oferta por 
        <span class="gradient-text">Tempo Limitado!</span>
      </h2>

      <!-- Descrição -->
      <p class="text-xl md:text-2xl text-gray-300 mb-8">
        Assine hoje e ganhe <strong class="text-primary-400">TESTE GRÁTIS de 24 horas</strong> + suporte prioritário!
      </p>

      <!-- Timer de urgência -->
      <div class="flex justify-center gap-4 mb-10">
        <div class="bg-dark-800 border border-primary-500/30 rounded-xl p-4 min-w-[80px]">
          <div class="text-3xl md:text-4xl font-bold text-primary-400">{{ hours }}</div>
          <div class="text-xs text-gray-500 uppercase tracking-wider">Horas</div>
        </div>
        <div class="bg-dark-800 border border-primary-500/30 rounded-xl p-4 min-w-[80px]">
          <div class="text-3xl md:text-4xl font-bold text-primary-400">{{ minutes }}</div>
          <div class="text-xs text-gray-500 uppercase tracking-wider">Min</div>
        </div>
        <div class="bg-dark-800 border border-primary-500/30 rounded-xl p-4 min-w-[80px]">
          <div class="text-3xl md:text-4xl font-bold text-primary-400">{{ seconds }}</div>
          <div class="text-xs text-gray-500 uppercase tracking-wider">Seg</div>
        </div>
      </div>

      <!-- Badges de benefícios -->
      <div class="flex flex-wrap justify-center gap-4 mb-10">
        <span class="inline-flex items-center px-4 py-2 bg-green-500/10 text-green-400 rounded-full text-sm font-medium">
          <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/>
          </svg>
          Teste Grátis 24h
        </span>
        <span class="inline-flex items-center px-4 py-2 bg-primary-500/10 text-primary-400 rounded-full text-sm font-medium">
          <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/>
          </svg>
          Ativação Imediata
        </span>
        <span class="inline-flex items-center px-4 py-2 bg-accent-500/10 text-accent-400 rounded-full text-sm font-medium">
          <svg class="w-4 h-4 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/>
          </svg>
          Suporte VIP
        </span>
      </div>

      <!-- CTA Button -->
      <a 
        href="#pricing" 
        class="inline-flex items-center btn-glow px-10 py-5 bg-gradient-to-r from-primary-500 to-accent-500 text-white font-bold text-xl rounded-full hover:from-primary-600 hover:to-accent-600 transition-all duration-300 transform hover:scale-105 shadow-lg shadow-primary-500/30 animate-pulse-glow"
      >
        Quero Aproveitar Agora!
        <svg class="w-6 h-6 ml-3" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
        </svg>
      </a>

      <!-- Aviso de vagas -->
      <p class="mt-6 text-gray-500 text-sm">
        ⚠️ Vagas limitadas para este plano promocional
      </p>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const hours = ref('23')
const minutes = ref('59')
const seconds = ref('59')

let interval = null

const updateTimer = () => {
  let h = parseInt(hours.value)
  let m = parseInt(minutes.value)
  let s = parseInt(seconds.value)

  s--
  if (s < 0) {
    s = 59
    m--
    if (m < 0) {
      m = 59
      h--
      if (h < 0) {
        // Reinicia o timer quando chega a zero
        h = 23
        m = 59
        s = 59
      }
    }
  }

  hours.value = h.toString().padStart(2, '0')
  minutes.value = m.toString().padStart(2, '0')
  seconds.value = s.toString().padStart(2, '0')
}

onMounted(() => {
  interval = setInterval(updateTimer, 1000)
})

onUnmounted(() => {
  if (interval) {
    clearInterval(interval)
  }
})
</script>
