<template>
  <div class="min-h-screen bg-dark-950 flex items-center justify-center px-4">
    <div class="max-w-xl text-center">
      <!-- Ícone de esgotado -->
      <div class="mb-8">
        <div class="inline-flex items-center justify-center w-24 h-24 bg-red-500/10 rounded-full">
          <svg class="w-16 h-16 text-red-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z"/>
          </svg>
        </div>
      </div>

      <!-- Título -->
      <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
        Promoção 
        <span class="text-red-400">Esgotada!</span> 😢
      </h1>

      <!-- Descrição -->
      <p class="text-lg text-gray-400 mb-8">
        Infelizmente as vagas para esta promoção já foram preenchidas. Mas não se preocupe, temos outras ofertas incríveis para você!
      </p>

      <!-- Card de alternativa -->
      <div class="glass-card rounded-2xl p-6 mb-8">
        <h3 class="text-white font-semibold mb-4">
          ✨ Quer ser avisado das próximas promoções?
        </h3>
        <p class="text-gray-400 mb-6">
          Deixe seu WhatsApp e seja o primeiro a saber quando abrirmos novas vagas promocionais!
        </p>
        
        <div class="flex flex-col sm:flex-row gap-3">
          <input 
            type="tel" 
            placeholder="(11) 99999-9999" 
            class="flex-1 px-4 py-3 bg-dark-800 border border-gray-700 rounded-xl text-white placeholder-gray-500 focus:outline-none focus:border-primary-500 transition-colors"
          />
          <button class="px-6 py-3 bg-gradient-to-r from-primary-500 to-accent-500 text-white font-semibold rounded-xl hover:from-primary-600 hover:to-accent-600 transition-all duration-300">
            Me Avise!
          </button>
        </div>
      </div>

      <!-- Alternativa -->
      <div class="bg-dark-800 rounded-xl p-6 mb-8">
        <p class="text-gray-400 mb-4">
          Ou confira nossos planos regulares com preços especiais:
        </p>
        <a 
          href="/#pricing" 
          class="inline-flex items-center btn-glow px-6 py-3 bg-gradient-to-r from-primary-500 to-primary-600 text-white font-semibold rounded-full hover:from-primary-600 hover:to-primary-700 transition-all duration-300"
        >
          Ver Planos Disponíveis
          <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
          </svg>
        </a>
      </div>

      <!-- Botão voltar -->
      <a 
        href="/" 
        class="inline-flex items-center text-gray-500 hover:text-gray-400 font-medium transition-colors"
      >
        <svg class="w-5 h-5 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 19l-7-7m0 0l7-7m-7 7h18"/>
        </svg>
        Voltar para a página inicial
      </a>
    </div>
  </div>
</template>

<script setup>
</script>
