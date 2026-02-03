<template>
  <section class="relative min-h-screen flex items-center justify-center overflow-hidden pt-20">
    <!-- Background com imagem e overlay -->
    <div class="absolute inset-0">
      <!-- Imagem de fundo -->
      <img 
        src="https://images.unsplash.com/photo-1593784991095-a205069470b6?q=80&w=2070&auto=format&fit=crop" 
        alt="Streaming Entertainment Background" 
        class="absolute inset-0 w-full h-full object-cover"
      />
      <!-- Overlay escuro com gradiente -->
      <div class="absolute inset-0 bg-gradient-to-br from-dark-950/95 via-dark-900/90 to-dark-950/95"></div>
      <!-- Grid pattern -->
      <div class="absolute inset-0 opacity-10" style="background-image: radial-gradient(circle at 1px 1px, rgba(14, 165, 233, 0.3) 1px, transparent 0); background-size: 40px 40px;"></div>
      
      <!-- Glow effects -->
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-primary-500/20 rounded-full filter blur-3xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-accent-500/20 rounded-full filter blur-3xl"></div>
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12 md:py-20">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- Conteúdo de texto -->
        <div class="text-center lg:text-left animate-fade-in">
          <!-- Badge -->
          <div class="inline-flex items-center px-4 py-2 bg-primary-500/10 border border-primary-500/30 rounded-full mb-6">
            <span class="w-2 h-2 bg-green-400 rounded-full animate-pulse mr-2"></span>
            <span class="text-primary-400 text-sm font-medium">Mais de 10.000 canais disponíveis</span>
          </div>

          <!-- Título principal -->
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-extrabold text-white leading-tight mb-6">
            Tenha todos os 
            <span class="gradient-text">canais, filmes</span> 
            e esportes ao vivo 
            <span class="gradient-text">na sua casa</span>
          </h1>

          <!-- Subtítulo -->
          <p class="text-lg md:text-xl text-gray-400 mb-8 max-w-xl mx-auto lg:mx-0">
            Acesso ilimitado ao melhor conteúdo de entretenimento. Filmes, séries, esportes e canais exclusivos em qualquer dispositivo, com qualidade HD e suporte 24h.
          </p>

          <!-- Botões CTA -->
          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <a 
              href="#pricing" 
              class="btn-glow px-8 py-4 bg-gradient-to-r from-primary-500 to-primary-600 text-white font-bold text-lg rounded-full hover:from-primary-600 hover:to-primary-700 transition-all duration-300 transform hover:scale-105 shadow-lg shadow-primary-500/30"
            >
              Assine Agora
              <svg class="inline-block w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 7l5 5m0 0l-5 5m5-5H6"/>
              </svg>
            </a>
            <a 
              href="#benefits" 
              class="px-8 py-4 border-2 border-gray-600 text-white font-semibold text-lg rounded-full hover:border-primary-500 hover:text-primary-400 transition-all duration-300"
            >
              Saiba Mais
            </a>
          </div>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-6 mt-12 pt-8 border-t border-gray-800">
            <div class="text-center lg:text-left">
              <div class="text-3xl md:text-4xl font-bold gradient-text">10K+</div>
              <div class="text-gray-500 text-sm">Canais ao Vivo</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-3xl md:text-4xl font-bold gradient-text">50K+</div>
              <div class="text-gray-500 text-sm">Filmes e Séries</div>
            </div>
            <div class="text-center lg:text-left">
              <div class="text-3xl md:text-4xl font-bold gradient-text">24/7</div>
              <div class="text-gray-500 text-sm">Suporte Online</div>
            </div>
          </div>
        </div>

        <!-- Imagem / Ilustração -->
        <div class="relative animate-float hidden lg:block">
          <div class="relative">
            <!-- TV Mockup -->
            <div class="relative bg-dark-800 rounded-3xl p-4 border border-gray-700 shadow-2xl">
              <div class="aspect-video bg-gradient-to-br from-primary-900 to-dark-900 rounded-2xl overflow-hidden">
                <!-- GIF de programação de TV -->
                <img 
                  src="https://media.giphy.com/media/3o7TKSjRrfIPjeiVyM/giphy.gif" 
                  alt="Streaming de conteúdo" 
                  class="w-full h-full object-cover"
                />
                <!-- Overlay com efeito de brilho -->
                <div class="absolute inset-0 bg-gradient-to-t from-dark-900/60 via-transparent to-transparent pointer-events-none"></div>
                <!-- Badge "AO VIVO" -->
                <div class="absolute top-3 left-3 flex items-center space-x-2 bg-red-600 px-3 py-1 rounded-full">
                  <span class="w-2 h-2 bg-white rounded-full animate-pulse"></span>
                  <span class="text-white text-xs font-bold uppercase tracking-wider">AO VIVO</span>
                </div>
              </div>
              
              <!-- Base da TV -->
              <div class="mt-4 flex justify-center">
                <div class="w-20 h-2 bg-gray-700 rounded-full"></div>
              </div>
            </div>

            <!-- Dispositivos flutuantes -->
            <div class="absolute -right-8 top-1/4 bg-dark-800 p-3 rounded-xl border border-gray-700 shadow-xl animate-pulse">
              <svg class="w-6 h-6 text-primary-400" fill="currentColor" viewBox="0 0 24 24">
                <path d="M17 1.01L7 1c-1.1 0-2 .9-2 2v18c0 1.1.9 2 2 2h10c1.1 0 2-.9 2-2V3c0-1.1-.9-1.99-2-1.99zM17 19H7V5h10v14z"/>
              </svg>
            </div>
            
            <div class="absolute -left-8 bottom-1/4 bg-dark-800 p-3 rounded-xl border border-gray-700 shadow-xl">
              <svg class="w-6 h-6 text-accent-400" fill="currentColor" viewBox="0 0 24 24">
                <path d="M20 18c1.1 0 1.99-.9 1.99-2L22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2H0v2h24v-2h-4zM4 6h16v10H4V6z"/>
              </svg>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <svg class="w-6 h-6 text-gray-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 14l-7 7m0 0l-7-7m7 7V3"/>
      </svg>
    </div>
  </section>
</template>

<script setup>
</script>
