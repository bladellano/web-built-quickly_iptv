<template>
  <section id="faq" class="py-20 md:py-32 relative">
    <!-- Background -->
    <div class="absolute inset-0 bg-dark-900">
      <div class="absolute top-0 left-0 w-full h-32 bg-gradient-to-b from-dark-950 to-transparent"></div>
    </div>

    <div class="relative z-10 max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Header -->
      <div class="text-center mb-16">
        <span class="inline-block px-4 py-2 bg-primary-500/10 text-primary-400 rounded-full text-sm font-medium mb-4">
          Dúvidas Frequentes
        </span>
        <h2 class="text-3xl md:text-4xl lg:text-5xl font-bold text-white mb-6">
          Perguntas 
          <span class="gradient-text">Frequentes</span>
        </h2>
        <p class="text-gray-400 text-lg max-w-2xl mx-auto">
          Tire suas dúvidas sobre nosso serviço de IPTV. Se não encontrar o que procura, entre em contato conosco.
        </p>
      </div>

      <!-- FAQ Accordion -->
      <div class="space-y-4">
        <div 
          v-for="(faq, index) in faqs" 
          :key="index"
          class="glass-card rounded-2xl overflow-hidden transition-all duration-300"
          :class="{ 'border-primary-500/50': activeIndex === index }"
        >
          <button 
            @click="toggle(index)"
            class="w-full px-6 py-5 flex items-center justify-between text-left hover:bg-dark-800/50 transition-colors"
          >
            <span class="text-lg font-semibold text-white pr-4">{{ faq.question }}</span>
            <svg 
              class="w-6 h-6 text-primary-400 transform transition-transform duration-300 flex-shrink-0"
              :class="{ 'rotate-180': activeIndex === index }"
              fill="none" 
              stroke="currentColor" 
              viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"/>
            </svg>
          </button>
          
          <transition
            enter-active-class="transition duration-300 ease-out"
            enter-from-class="opacity-0 -translate-y-2"
            enter-to-class="opacity-100 translate-y-0"
            leave-active-class="transition duration-200 ease-in"
            leave-from-class="opacity-100 translate-y-0"
            leave-to-class="opacity-0 -translate-y-2"
          >
            <div v-if="activeIndex === index" class="px-6 pb-5">
              <p class="text-gray-400 leading-relaxed">{{ faq.answer }}</p>
            </div>
          </transition>
        </div>
      </div>

      <!-- CTA após FAQ -->
      <div class="mt-12 text-center">
        <p class="text-gray-400 mb-4">Ainda tem dúvidas?</p>
        <a 
          href="#" 
          class="inline-flex items-center text-primary-400 hover:text-primary-300 font-medium transition-colors"
        >
          Fale com nosso suporte
          <svg class="w-5 h-5 ml-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M8 12h.01M12 12h.01M16 12h.01M21 12c0 4.418-4.03 8-9 8a9.863 9.863 0 01-4.255-.949L3 20l1.395-3.72C3.512 15.042 3 13.574 3 12c0-4.418 4.03-8 9-8s9 3.582 9 8z"/>
          </svg>
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const activeIndex = ref(null)

const toggle = (index) => {
  activeIndex.value = activeIndex.value === index ? null : index
}

const faqs = [
  {
    question: 'O que é IPTV e como funciona?',
    answer: 'IPTV (Internet Protocol Television) é um serviço de streaming que permite assistir canais de TV, filmes e séries pela internet. Você recebe seus dados de acesso e pode assistir em qualquer dispositivo compatível, como Smart TV, celular, computador ou TV Box.'
  },
  {
    question: 'Quais dispositivos são compatíveis?',
    answer: 'Nosso serviço é compatível com Smart TVs (Samsung, LG, Sony), celulares Android e iOS, computadores (Windows e Mac), tablets, TV Box, Fire Stick, Chromecast e qualquer dispositivo com aplicativo de IPTV.'
  },
  {
    question: 'Qual a qualidade do streaming?',
    answer: 'Oferecemos conteúdo em qualidade SD, HD e 4K (quando disponível). A qualidade depende da sua velocidade de internet. Recomendamos no mínimo 10 Mbps para HD e 25 Mbps para 4K.'
  },
  {
    question: 'O serviço trava ou tem buffer?',
    answer: 'Nossos servidores são otimizados para máxima estabilidade. Com uma boa conexão de internet, o serviço funciona sem travamentos. Caso tenha problemas, nosso suporte 24h está disponível para ajudar.'
  },
  {
    question: 'Quais são as formas de pagamento?',
    answer: 'Aceitamos cartão de crédito, débito, Pix e boleto bancário. O pagamento é processado de forma segura e você recebe seus dados de acesso imediatamente após a confirmação.'
  },
  {
    question: 'Posso cancelar a qualquer momento?',
    answer: 'Sim! Não há fidelidade. Você pode cancelar seu plano a qualquer momento sem multas ou taxas adicionais. Basta entrar em contato com nosso suporte.'
  },
  {
    question: 'Quantos dispositivos posso usar?',
    answer: 'Cada plano permite conexões simultâneas. O plano básico permite 1 tela, o intermediário 2 telas e o premium até 4 telas ao mesmo tempo.'
  },
  {
    question: 'Vocês oferecem teste grátis?',
    answer: 'Sim! Oferecemos teste gratuito de 24 horas para novos clientes. Assim você pode conhecer a qualidade do nosso serviço antes de assinar.'
  }
]
</script>
