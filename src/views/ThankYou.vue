<template>
  <div class="min-h-screen bg-dark-950 flex items-center justify-center px-4">
    <div class="max-w-xl text-center">
      <!-- Ícone de sucesso -->
      <div class="mb-8">
        <div class="inline-flex items-center justify-center w-24 h-24 bg-green-500/10 rounded-full">
          <svg class="w-16 h-16 text-green-400" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"/>
          </svg>
        </div>
      </div>

      <!-- Título -->
      <h1 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
        Assinatura 
        <span class="gradient-text">Confirmada!</span> 🎉
      </h1>

      <!-- Descrição -->
      <p class="text-lg text-gray-400 mb-8">
        Parabéns! Sua assinatura foi recebida com sucesso. Em breve você receberá um e-mail com os dados de acesso ao seu IPTV Premium.
      </p>

      <!-- Card de informações -->
      <div class="glass-card rounded-2xl p-6 mb-8 text-left">
        <h3 class="text-white font-semibold mb-4 flex items-center">
          <svg class="w-5 h-5 text-primary-400 mr-2" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"/>
          </svg>
          Próximos passos:
        </h3>
        <ul class="space-y-3 text-gray-400">
          <li class="flex items-start">
            <span class="w-6 h-6 bg-primary-500/20 text-primary-400 rounded-full flex items-center justify-center text-sm font-bold mr-3 flex-shrink-0">1</span>
            <span>Verifique seu e-mail (inclusive a pasta de spam)</span>
          </li>
          <li class="flex items-start">
            <span class="w-6 h-6 bg-primary-500/20 text-primary-400 rounded-full flex items-center justify-center text-sm font-bold mr-3 flex-shrink-0">2</span>
            <span>Siga as instruções de instalação no e-mail</span>
          </li>
          <li class="flex items-start">
            <span class="w-6 h-6 bg-primary-500/20 text-primary-400 rounded-full flex items-center justify-center text-sm font-bold mr-3 flex-shrink-0">3</span>
            <span>Aproveite todo o conteúdo disponível!</span>
          </li>
        </ul>
      </div>

      <!-- Suporte -->
      <div class="bg-dark-800 rounded-xl p-4 mb-8">
        <p class="text-gray-500 text-sm">
          Dúvidas? Entre em contato com nosso suporte via 
          <a href="#" class="text-primary-400 hover:text-primary-300 transition-colors">WhatsApp</a> 
          ou e-mail.
        </p>
      </div>

      <!-- Botão voltar -->
      <a 
        href="/" 
        class="inline-flex items-center text-primary-400 hover:text-primary-300 font-medium transition-colors"
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
