<template>
  <section id="pricing" class="py-20 md:py-32 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0 bg-dark-950">
      <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-primary-500/10 rounded-full filter blur-3xl"></div>
      <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-accent-500/10 rounded-full filter blur-3xl"></div>
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <div class="text-center mb-16">
        <span class="inline-block px-4 py-2 bg-primary-500/10 text-primary-400 rounded-full text-sm font-medium mb-4">
          Planos e Preços
        </span>
        <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
          Escolha seu 
          <span class="gradient-text">Plano Ideal</span>
        </h2>
        <p class="text-gray-400 text-lg max-w-2xl mx-auto">
          Temos o plano perfeito para você. Todos incluem acesso completo a canais, filmes e séries.
        </p>
      </div>

      <!-- Pricing Cards -->
      <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <div 
          v-for="(plan, index) in plans" 
          :key="index"
          class="relative glass-card rounded-3xl p-8 transition-all duration-300 transform hover:-translate-y-2"
          :class="plan.featured ? 'border-2 border-primary-500 shadow-lg shadow-primary-500/20' : 'hover:border-primary-500/30'"
        >
          <!-- Badge de destaque -->
          <div 
            v-if="plan.featured" 
            class="absolute -top-4 left-1/2 transform -translate-x-1/2 px-4 py-1 bg-gradient-to-r from-primary-500 to-accent-500 text-white text-sm font-bold rounded-full"
          >
            Mais Popular
          </div>

          <!-- Nome do plano -->
          <div class="text-center mb-6">
            <h3 class="text-xl font-bold text-white mb-2">{{ plan.name }}</h3>
            <p class="text-gray-500 text-sm">{{ plan.description }}</p>
          </div>

          <!-- Preço -->
          <div class="text-center mb-8">
            <div class="flex items-center justify-center">
              <span class="text-gray-500 text-lg">R$</span>
              <span class="text-5xl font-bold text-white mx-1">{{ plan.price }}</span>
              <span class="text-gray-500">/mês</span>
            </div>
            <p v-if="plan.oldPrice" class="text-gray-600 line-through text-sm mt-1">
              De R$ {{ plan.oldPrice }}
            </p>
          </div>

          <!-- Features -->
          <ul class="space-y-4 mb-8">
            <li 
              v-for="(feature, fIndex) in plan.features" 
              :key="fIndex"
              class="flex items-start"
            >
              <svg class="w-5 h-5 text-green-400 mr-3 mt-0.5 flex-shrink-0" fill="currentColor" viewBox="0 0 24 24">
                <path d="M9 16.17L4.83 12l-1.42 1.41L9 19 21 7l-1.41-1.41z"/>
              </svg>
              <span class="text-gray-300">{{ feature }}</span>
            </li>
          </ul>

          <!-- CTA Button -->
          <a 
            :href="plan.link"
            class="block w-full py-4 text-center font-bold rounded-full transition-all duration-300 transform hover:scale-105"
            :class="plan.featured 
              ? 'bg-gradient-to-r from-primary-500 to-accent-500 text-white shadow-lg shadow-primary-500/30 hover:from-primary-600 hover:to-accent-600' 
              : 'bg-dark-800 text-white border border-gray-700 hover:border-primary-500 hover:text-primary-400'"
          >
            {{ plan.cta }}
          </a>
        </div>
      </div>

      <!-- Garantia -->
      <div class="mt-16 text-center">
        <div class="inline-flex items-center glass-card rounded-2xl px-8 py-4">
          <svg class="w-12 h-12 text-green-400 mr-4" fill="currentColor" viewBox="0 0 24 24">
            <path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm-2 16l-4-4 1.41-1.41L10 14.17l6.59-6.59L18 9l-8 8z"/>
          </svg>
          <div class="text-left">
            <h4 class="text-white font-bold">Garantia de 7 Dias</h4>
            <p class="text-gray-400 text-sm">Se não gostar, devolvemos 100% do seu dinheiro</p>
          </div>
        </div>
      </div>

      <!-- Métodos de pagamento -->
      <div class="mt-12 text-center">
        <p class="text-gray-500 text-sm mb-4">Formas de pagamento aceitas:</p>
        <div class="flex justify-center items-center gap-6 flex-wrap">
          <div class="flex items-center text-gray-400">
            <svg class="w-8 h-8 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M20 4H4c-1.11 0-1.99.89-1.99 2L2 18c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V6c0-1.11-.89-2-2-2zm0 14H4v-6h16v6zm0-10H4V6h16v2z"/>
            </svg>
            <span class="text-sm">Cartão</span>
          </div>
          <div class="flex items-center text-gray-400">
            <svg class="w-8 h-8 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M17.21 9l-4.38-6.56c-.19-.28-.51-.42-.83-.42-.32 0-.64.14-.83.43L6.79 9H2c-.55 0-1 .45-1 1 0 .09.01.18.04.27l2.54 9.27c.23.84 1 1.46 1.92 1.46h13c.92 0 1.69-.62 1.93-1.46l2.54-9.27L23 10c0-.55-.45-1-1-1h-4.79zM9 9l3-4.4L15 9H9zm3 8c-1.1 0-2-.9-2-2s.9-2 2-2 2 .9 2 2-.9 2-2 2z"/>
            </svg>
            <span class="text-sm">Pix</span>
          </div>
          <div class="flex items-center text-gray-400">
            <svg class="w-8 h-8 mr-2" fill="currentColor" viewBox="0 0 24 24">
              <path d="M14 2H6c-1.1 0-1.99.9-1.99 2L4 20c0 1.1.89 2 1.99 2H18c1.1 0 2-.9 2-2V8l-6-6zm2 16H8v-2h8v2zm0-4H8v-2h8v2zm-3-5V3.5L18.5 9H13z"/>
            </svg>
            <span class="text-sm">Boleto</span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const plans = [
  {
    name: 'Básico',
    description: 'Ideal para uso individual',
    price: '24,90',
    oldPrice: '39,90',
    features: [
      'Acesso a todos os canais',
      'Filmes e séries on demand',
      '1 tela simultânea',
      'Qualidade HD',
      'Suporte por WhatsApp'
    ],
    cta: 'Assinar Básico',
    link: '/obrigado',
    featured: false
  },
  {
    name: 'Premium',
    description: 'O mais escolhido pelos clientes',
    price: '34,90',
    oldPrice: '59,90',
    features: [
      'Tudo do plano Básico',
      '2 telas simultâneas',
      'Qualidade Full HD',
      'Canais de esportes premium',
      'Suporte prioritário 24h'
    ],
    cta: 'Assinar Premium',
    link: '/obrigado',
    featured: true
  },
  {
    name: 'Família',
    description: 'Perfeito para toda a família',
    price: '49,90',
    oldPrice: '79,90',
    features: [
      'Tudo do plano Premium',
      '4 telas simultâneas',
      'Qualidade 4K',
      'Conteúdo infantil',
      'Suporte VIP + instalação remota'
    ],
    cta: 'Assinar Família',
    link: '/obrigado',
    featured: false
  }
]
</script>
