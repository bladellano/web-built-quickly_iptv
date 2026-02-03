<template>
  <section id="benefits" class="py-20 md:py-32 relative overflow-hidden">
    <!-- Background -->
    <div class="absolute inset-0 bg-dark-900">
      <div class="absolute top-0 left-0 w-full h-32 bg-gradient-to-b from-dark-950 to-transparent"></div>
      <div class="absolute bottom-0 left-0 w-full h-32 bg-gradient-to-t from-dark-950 to-transparent"></div>
    </div>

    <div class="relative z-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header da seção -->
      <div class="text-center mb-16">
        <span class="inline-block px-4 py-2 bg-primary-500/10 text-primary-400 rounded-full text-sm font-medium mb-4">
          Por que escolher nosso IPTV?
        </span>
        <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
          Tudo que você precisa em 
          <span class="gradient-text">um só lugar</span>
        </h2>
        <p class="text-gray-400 text-lg max-w-2xl mx-auto">
          Oferecemos a melhor experiência em streaming com qualidade superior, variedade incomparável e suporte dedicado.
        </p>
      </div>

      <!-- Grid de benefícios -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(benefit, index) in benefits" 
          :key="index"
          class="glass-card rounded-2xl p-8 hover:border-primary-500/50 transition-all duration-300 transform hover:-translate-y-2 group"
        >
          <div 
            class="w-14 h-14 rounded-xl flex items-center justify-center mb-6 transition-all duration-300 group-hover:scale-110"
            :class="benefit.bgColor"
          >
            <component :is="benefit.icon" class="w-7 h-7" :class="benefit.iconColor" />
          </div>
          <h3 class="text-xl font-bold text-white mb-3">{{ benefit.title }}</h3>
          <p class="text-gray-400">{{ benefit.description }}</p>
        </div>
      </div>

      <!-- Seção de dispositivos compatíveis -->
      <div id="about" class="mt-20 glass-card rounded-3xl p-8 md:p-12">
        <div class="grid lg:grid-cols-2 gap-12 items-center">
          <div>
            <h3 class="text-2xl md:text-3xl font-bold text-white mb-6">
              Assista em 
              <span class="gradient-text">qualquer dispositivo</span>
            </h3>
            <p class="text-gray-400 mb-8">
              Nosso serviço é compatível com todos os principais dispositivos. Comece a assistir na TV e continue no celular, ou vice-versa. A escolha é sua!
            </p>
            
            <div class="grid grid-cols-2 gap-4">
              <div 
                v-for="device in devices" 
                :key="device.name"
                class="flex items-center space-x-3 p-4 bg-dark-800 rounded-xl border border-gray-700 hover:border-primary-500/50 transition-colors"
              >
                <component :is="device.icon" class="w-6 h-6 text-primary-400" />
                <span class="text-white font-medium">{{ device.name }}</span>
              </div>
            </div>
          </div>
          
          <!-- Ilustração de dispositivos -->
          <div class="flex justify-center">
            <div class="relative">
              <div class="w-64 h-40 bg-dark-800 rounded-xl border border-gray-700 flex items-center justify-center">
                <svg class="w-16 h-16 text-primary-400" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M21 3H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h5v2h8v-2h5c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 14H3V5h18v12z"/>
                </svg>
              </div>
              <div class="absolute -right-8 -bottom-8 w-20 h-32 bg-dark-800 rounded-xl border border-gray-700 flex items-center justify-center shadow-xl">
                <svg class="w-8 h-8 text-accent-400" fill="currentColor" viewBox="0 0 24 24">
                  <path d="M17 1.01L7 1c-1.1 0-2 .9-2 2v18c0 1.1.9 2 2 2h10c1.1 0 2-.9 2-2V3c0-1.1-.9-1.99-2-1.99zM17 19H7V5h10v14z"/>
                </svg>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { h } from 'vue'

// Ícones como componentes funcionais
const TvIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M21 3H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h5v2h8v-2h5c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 14H3V5h18v12z' })
])

const MovieIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M18 4l2 4h-3l-2-4h-2l2 4h-3l-2-4H8l2 4H7L5 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V4h-4z' })
])

const SportsIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm1 17.93c-3.94-.49-7-3.85-7-7.93s3.05-7.44 7-7.93v15.86zm2-15.86c1.03.13 2 .45 2.87.93H13v-.93zM13 7h5.24c.25.31.48.65.68 1H13V7zm0 3h6.74c.08.33.15.66.19 1H13v-1zm0 9.93V19h2.87c-.87.48-1.84.8-2.87.93zM18.24 17H13v-1h5.92c-.2.35-.43.69-.68 1zm1.5-3H13v-1h6.93c-.04.34-.11.67-.19 1z' })
])

const SpeedIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M20.38 8.57l-1.23 1.85a8 8 0 0 1-.22 7.58H5.07A8 8 0 0 1 15.58 6.85l1.85-1.23A10 10 0 0 0 3.35 19a2 2 0 0 0 1.72 1h13.85a2 2 0 0 0 1.74-1 10 10 0 0 0-.27-10.44zm-9.79 6.84a2 2 0 0 0 2.83 0l5.66-8.49-8.49 5.66a2 2 0 0 0 0 2.83z' })
])

const SupportIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 1c-4.97 0-9 4.03-9 9v7c0 1.66 1.34 3 3 3h3v-8H5v-2c0-3.87 3.13-7 7-7s7 3.13 7 7v2h-4v8h3c1.66 0 3-1.34 3-3v-7c0-4.97-4.03-9-9-9z' })
])

const QualityIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 15.5h-1.5V14h-1v3H8v-3H7v4.5H5.5v-5c0-.55.45-1 1-1H11c.55 0 1 .45 1 1v5zm3.5 0H14v-6h3.5c.55 0 1 .45 1 1V16c0 .55-.45 1-1 1h-2v1.5zM10 5.5v6H8.5V7H7V5.5h3zm6.5 7H14v1.5h2.5V15H14v-2.5c0-.55.45-1 1-1h2.5c.55 0 1 .45 1 1v2c0 .55-.45 1-1 1z' })
])

const PhoneIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M17 1.01L7 1c-1.1 0-2 .9-2 2v18c0 1.1.9 2 2 2h10c1.1 0 2-.9 2-2V3c0-1.1-.9-1.99-2-1.99zM17 19H7V5h10v14z' })
])

const LaptopIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M20 18c1.1 0 1.99-.9 1.99-2L22 6c0-1.1-.9-2-2-2H4c-1.1 0-2 .9-2 2v10c0 1.1.9 2 2 2H0v2h24v-2h-4zM4 6h16v10H4V6z' })
])

const TabletIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M21 4H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h18c1.1 0 1.99-.9 1.99-2L23 6c0-1.1-.9-2-2-2zm-2 14H5V6h14v12z' })
])

const BoxIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M20 2H4c-1.1 0-2 .9-2 2v16c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V4c0-1.1-.9-2-2-2zM8 20H4v-4h4v4zm0-6H4v-4h4v4zm0-6H4V4h4v4zm6 12h-4v-4h4v4zm0-6h-4v-4h4v4zm0-6h-4V4h4v4zm6 12h-4v-4h4v4zm0-6h-4v-4h4v4zm0-6h-4V4h4v4z' })
])

const benefits = [
  {
    icon: TvIcon,
    title: 'Mais de 10.000 Canais',
    description: 'Acesso a canais nacionais e internacionais, incluindo esportes, filmes, séries, notícias e muito mais.',
    bgColor: 'bg-primary-500/10',
    iconColor: 'text-primary-400'
  },
  {
    icon: MovieIcon,
    title: 'Filmes e Séries On Demand',
    description: 'Biblioteca com mais de 50.000 títulos para assistir quando quiser, com lançamentos atualizados.',
    bgColor: 'bg-accent-500/10',
    iconColor: 'text-accent-400'
  },
  {
    icon: SportsIcon,
    title: 'Esportes ao Vivo',
    description: 'Futebol, UFC, NBA, F1 e muito mais. Nunca mais perca um jogo do seu time favorito.',
    bgColor: 'bg-green-500/10',
    iconColor: 'text-green-400'
  },
  {
    icon: SpeedIcon,
    title: 'Alta Velocidade',
    description: 'Servidores otimizados para streaming sem travamentos, buffering mínimo e máxima estabilidade.',
    bgColor: 'bg-yellow-500/10',
    iconColor: 'text-yellow-400'
  },
  {
    icon: SupportIcon,
    title: 'Suporte 24/7',
    description: 'Equipe de suporte disponível 24 horas por dia, 7 dias por semana para te ajudar.',
    bgColor: 'bg-red-500/10',
    iconColor: 'text-red-400'
  },
  {
    icon: QualityIcon,
    title: 'Qualidade HD/4K',
    description: 'Conteúdo em alta definição para você aproveitar cada detalhe com a melhor qualidade.',
    bgColor: 'bg-blue-500/10',
    iconColor: 'text-blue-400'
  }
]

const devices = [
  { name: 'Smart TV', icon: TvIcon },
  { name: 'Celular', icon: PhoneIcon },
  { name: 'Computador', icon: LaptopIcon },
  { name: 'TV Box', icon: BoxIcon }
]
</script>
