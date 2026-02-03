<template>
  <section id="faq" class="section bg-dark-lighter py-24">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="section-title">Perguntas Frequentes</h2>
        <p class="section-subtitle">
          Tire suas dúvidas sobre nosso serviço
        </p>
      </div>

      <div class="max-w-3xl mx-auto space-y-4">
        <div 
          v-for="(faq, index) in faqs" 
          :key="index"
          class="faq-item"
        >
          <button 
            @click="toggleFaq(index)"
            class="faq-question"
            :class="{ 'active': openFaq === index }"
          >
            <span class="faq-question-text">{{ faq.question }}</span>
            <svg 
              class="faq-icon"
              :class="{ 'rotate-180': openFaq === index }"
              fill="none" 
              stroke="currentColor" 
              viewBox="0 0 24 24"
            >
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
          </button>
          
          <transition
            enter-active-class="transition-all duration-300 ease-out"
            enter-from-class="max-h-0 opacity-0"
            enter-to-class="max-h-96 opacity-100"
            leave-active-class="transition-all duration-200 ease-in"
            leave-from-class="max-h-96 opacity-100"
            leave-to-class="max-h-0 opacity-0"
          >
            <div v-if="openFaq === index" class="faq-answer">
              {{ faq.answer }}
            </div>
          </transition>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const openFaq = ref(null)

const faqs = ref([
  {
    question: 'Como funciona o serviço de IPTV?',
    answer: 'Nosso serviço de IPTV funciona através de streaming pela internet. Você recebe acesso a uma plataforma com mais de 1500 canais que podem ser assistidos em qualquer dispositivo conectado à internet, como Smart TV, celular, tablet ou computador. É simples, prático e com qualidade HD/4K.'
  },
  {
    question: 'Quais dispositivos são compatíveis?',
    answer: 'Nosso serviço é compatível com Smart TVs (Samsung, LG, Android TV), smartphones e tablets (iOS e Android), computadores (Windows, Mac, Linux), TV Box, Amazon Fire Stick e qualquer dispositivo que suporte aplicativos de IPTV. Oferecemos suporte completo para configuração.'
  },
  {
    question: 'Posso assistir em mais de um dispositivo?',
    answer: 'Sim! Dependendo do plano escolhido, você pode assistir simultaneamente em até 2 ou 3 dispositivos. Isso significa que você e sua família podem assistir canais diferentes ao mesmo tempo sem problemas.'
  },
  {
    question: 'Quais são as formas de pagamento?',
    answer: 'Aceitamos diversas formas de pagamento incluindo cartão de crédito, cartão de débito, PIX e boleto bancário. O pagamento é processado de forma segura através de plataformas certificadas. Você também pode escolher entre planos mensais, trimestrais ou anuais.'
  },
  {
    question: 'Tem período de teste?',
    answer: 'Sim! Oferecemos 7 dias de garantia. Se você não ficar satisfeito com o serviço dentro desse período, devolvemos 100% do seu dinheiro sem perguntas. Queremos que você tenha certeza da qualidade antes de se comprometer.'
  },
  {
    question: 'Como faço para cancelar a assinatura?',
    answer: 'Você pode cancelar sua assinatura a qualquer momento, sem burocracia e sem multas. Basta entrar em contato com nosso suporte através do WhatsApp ou e-mail e processaremos seu cancelamento imediatamente. Não há período de fidelidade.'
  },
  {
    question: 'O serviço tem travamentos?',
    answer: 'Nossos servidores são de alta performance e garantem estabilidade máxima. Para uma experiência sem travamentos, recomendamos uma conexão de internet de pelo menos 10 Mbps. Com infraestrutura premium e monitoramento 24/7, mantemos a qualidade em todos os momentos.'
  },
  {
    question: 'Vocês oferecem suporte técnico?',
    answer: 'Sim! Nossa equipe de suporte está disponível 24 horas por dia, 7 dias por semana para ajudar você. Oferecemos suporte via WhatsApp, e-mail e chat online. Auxiliamos desde a instalação até a resolução de qualquer problema técnico.'
  }
])

const toggleFaq = (index) => {
  openFaq.value = openFaq.value === index ? null : index
}
</script>

<style scoped>
.faq-item {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  overflow: hidden;
  transition: all 0.3s ease;
}

.faq-item:hover {
  border-color: rgba(99, 102, 241, 0.3);
}

.faq-question {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.5rem;
  background: transparent;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  text-align: left;
}

.faq-question.active {
  background: rgba(99, 102, 241, 0.1);
}

.faq-question-text {
  color: white;
  font-size: 1.125rem;
  font-weight: 600;
  padding-right: 1rem;
}

.faq-icon {
  width: 24px;
  height: 24px;
  color: #6366f1;
  transition: transform 0.3s ease;
  flex-shrink: 0;
}

.faq-answer {
  padding: 0 1.5rem 1.5rem;
  color: rgba(255, 255, 255, 0.7);
  line-height: 1.7;
  overflow: hidden;
}
</style>
