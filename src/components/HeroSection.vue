<template>
  <section 
    id="hero" 
    class="relative min-h-screen flex items-center justify-center overflow-hidden bg-gradient-to-br from-dark via-dark-lighter to-dark pt-20"
  >
    <!-- Background Animation -->
    <div class="absolute inset-0 overflow-hidden">
      <div class="absolute top-1/4 -left-48 w-96 h-96 bg-primary/20 rounded-full blur-3xl animate-pulse-slow"></div>
      <div class="absolute bottom-1/4 -right-48 w-96 h-96 bg-purple-600/20 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 1s;"></div>
    </div>

    <!-- Content -->
    <div class="section-container relative z-10">
      <div class="grid lg:grid-cols-2 gap-12 items-center">
        <!-- Text Content -->
        <div class="text-center lg:text-left space-y-8 animate-fade-in">
          <div class="inline-block px-4 py-2 bg-primary/10 border border-primary/30 rounded-full text-primary text-sm font-semibold mb-4">
            🔥 Promoção por Tempo Limitado
          </div>
          
          <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight">
            Mais de <span class="bg-gradient-to-r from-primary to-purple-600 bg-clip-text text-transparent">1500 canais</span> 
            <br />na palma da sua mão
          </h1>
          
          <p class="text-xl text-gray-400 max-w-2xl">
            Acesse milhares de canais de TV, filmes, séries, esportes e muito mais. 
            Qualidade HD/4K e suporte em múltiplos dispositivos.
          </p>

          <div class="flex flex-col sm:flex-row gap-4 justify-center lg:justify-start">
            <a href="#assinar" class="btn-primary text-lg">
              Assine Agora por R$ 49,90/mês
            </a>
            <a href="#sobre" class="btn-secondary">
              Saiba Mais
            </a>
          </div>

          <!-- Stats -->
          <div class="grid grid-cols-3 gap-6 pt-8 border-t border-gray-800">
            <div>
              <div class="text-3xl font-bold text-primary">1500+</div>
              <div class="text-sm text-gray-400">Canais</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-primary">HD/4K</div>
              <div class="text-sm text-gray-400">Qualidade</div>
            </div>
            <div>
              <div class="text-3xl font-bold text-primary">24/7</div>
              <div class="text-sm text-gray-400">Suporte</div>
            </div>
          </div>
        </div>

        <!-- Image/Visual -->
        <div class="relative lg:h-[600px] flex items-center justify-center animate-slide-up">
          <div class="relative w-full max-w-md lg:max-w-lg">
            <!-- TV Frame -->
            <div class="relative bg-gradient-to-br from-dark-light to-dark-lighter rounded-3xl p-6 shadow-2xl border border-gray-800">
              <div class="relative aspect-video bg-gradient-to-br from-primary/20 to-purple-600/20 rounded-2xl overflow-hidden">
                <!-- Simulated Screen Content -->
                <div class="absolute inset-0 bg-black/50 flex items-center justify-center">
                  <div class="text-center space-y-4">
                    <div class="w-20 h-20 mx-auto bg-primary/30 rounded-full flex items-center justify-center backdrop-blur-sm">
                      <svg class="w-10 h-10 text-primary" fill="currentColor" viewBox="0 0 20 20">
                        <path d="M10 18a8 8 0 100-16 8 8 0 000 16zM9.555 7.168A1 1 0 008 8v4a1 1 0 001.555.832l3-2a1 1 0 000-1.664l-3-2z" />
                      </svg>
                    </div>
                    <p class="text-sm text-gray-400">Transmissão em Alta Qualidade</p>
                  </div>
                </div>
                <!-- Floating Elements -->
                <div class="absolute top-4 left-4 bg-red-600 text-white text-xs px-2 py-1 rounded font-bold">
                  AO VIVO
                </div>
              </div>
            </div>

            <!-- Floating Cards -->
            <div class="absolute -bottom-6 -left-6 bg-dark-lighter border border-gray-800 rounded-xl p-4 shadow-xl animate-pulse-slow">
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-primary/20 rounded-lg flex items-center justify-center">
                  <span class="text-2xl">🎬</span>
                </div>
                <div>
                  <div class="text-sm font-semibold">Filmes</div>
                  <div class="text-xs text-gray-400">500+ títulos</div>
                </div>
              </div>
            </div>

            <div class="absolute -top-6 -right-6 bg-dark-lighter border border-gray-800 rounded-xl p-4 shadow-xl animate-pulse-slow" style="animation-delay: 0.5s;">
              <div class="flex items-center gap-3">
                <div class="w-12 h-12 bg-purple-600/20 rounded-lg flex items-center justify-center">
                  <span class="text-2xl">⚽</span>
                </div>
                <div>
                  <div class="text-sm font-semibold">Esportes</div>
                  <div class="text-xs text-gray-400">Ao vivo</div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll Indicator -->
    <div class="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
      <a href="#sobre" class="text-gray-400 hover:text-white transition-colors">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
        </svg>
      </a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection'
}
</script>
