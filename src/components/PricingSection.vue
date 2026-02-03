<template>
  <section id="assinar" class="section bg-dark py-24">
    <div class="section-container">
      <div class="text-center mb-16">
        <h2 class="section-title">Escolha seu Plano</h2>
        <p class="section-subtitle">
          Sem compromisso. Cancele quando quiser.
        </p>
      </div>

      <div class="grid md:grid-cols-3 gap-8 max-w-5xl mx-auto">
        <!-- Plano Mensal -->
        <div class="pricing-card">
          <div class="pricing-header">
            <h3 class="pricing-title">Mensal</h3>
            <div class="pricing-price">
              <span class="currency">R$</span>
              <span class="amount">49</span>
              <span class="period">,90/mês</span>
            </div>
          </div>
          
          <ul class="pricing-features">
            <li>✅ 1500+ Canais HD/4K</li>
            <li>✅ Filmes e Séries</li>
            <li>✅ 1 Dispositivo</li>
            <li>✅ Suporte 24/7</li>
            <li>✅ Sem Fidelidade</li>
          </ul>

          <button @click="selectPlan('mensal')" class="pricing-button">
            Assinar Agora
          </button>
        </div>

        <!-- Plano Trimestral (Popular) -->
        <div class="pricing-card featured">
          <div class="popular-badge">MAIS POPULAR</div>
          <div class="pricing-header">
            <h3 class="pricing-title">Trimestral</h3>
            <div class="pricing-price">
              <span class="currency">R$</span>
              <span class="amount">39</span>
              <span class="period">,90/mês</span>
            </div>
            <div class="savings">Economize R$ 30</div>
          </div>
          
          <ul class="pricing-features">
            <li>✅ 1500+ Canais HD/4K</li>
            <li>✅ Filmes e Séries</li>
            <li>✅ 2 Dispositivos</li>
            <li>✅ Suporte Prioritário</li>
            <li>✅ Canais Premium</li>
            <li>✅ 7 Dias de Garantia</li>
          </ul>

          <button @click="selectPlan('trimestral')" class="pricing-button featured">
            Assinar Agora
          </button>
        </div>

        <!-- Plano Anual -->
        <div class="pricing-card">
          <div class="best-value-badge">MELHOR VALOR</div>
          <div class="pricing-header">
            <h3 class="pricing-title">Anual</h3>
            <div class="pricing-price">
              <span class="currency">R$</span>
              <span class="amount">29</span>
              <span class="period">,90/mês</span>
            </div>
            <div class="savings">Economize R$ 240</div>
          </div>
          
          <ul class="pricing-features">
            <li>✅ 1500+ Canais HD/4K</li>
            <li>✅ Filmes e Séries</li>
            <li>✅ 3 Dispositivos</li>
            <li>✅ Suporte VIP</li>
            <li>✅ Todos os Canais Premium</li>
            <li>✅ Conteúdo Exclusivo</li>
            <li>✅ 30 Dias de Garantia</li>
          </ul>

          <button @click="selectPlan('anual')" class="pricing-button">
            Assinar Agora
          </button>
        </div>
      </div>

      <!-- Payment Methods -->
      <div class="mt-16 text-center">
        <p class="text-gray-400 mb-4">Formas de Pagamento</p>
        <div class="flex justify-center gap-6 flex-wrap items-center">
          <div class="payment-method">💳 Cartão de Crédito</div>
          <div class="payment-method">💰 PIX</div>
          <div class="payment-method">🏦 Boleto</div>
          <div class="payment-method">💵 Débito</div>
        </div>
      </div>

      <!-- Guarantee -->
      <div class="mt-12 max-w-2xl mx-auto">
        <div class="guarantee-box">
          <div class="guarantee-icon">🛡️</div>
          <div>
            <h4 class="guarantee-title">Garantia de 7 Dias</h4>
            <p class="guarantee-text">
              Se você não gostar do serviço, devolvemos 100% do seu dinheiro. 
              Sem perguntas, sem complicação.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { useRouter } from 'vue-router'

const router = useRouter()

const selectPlan = (plan) => {
  // Simula o processo de seleção de plano
  console.log(`Plano selecionado: ${plan}`)
  
  // Aqui você pode adicionar lógica de pagamento real
  // Por enquanto, vamos redirecionar para a página de obrigado
  
  // Simula um pequeno delay como se estivesse processando
  setTimeout(() => {
    router.push('/obrigado')
  }, 500)
}
</script>

<style scoped>
.pricing-card {
  background: rgba(255, 255, 255, 0.03);
  border: 2px solid rgba(255, 255, 255, 0.1);
  border-radius: 1.5rem;
  padding: 2rem;
  position: relative;
  transition: all 0.3s ease;
}

.pricing-card:hover {
  transform: translateY(-8px);
  border-color: rgba(99, 102, 241, 0.5);
  box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
}

.pricing-card.featured {
  background: linear-gradient(135deg, rgba(99, 102, 241, 0.1), rgba(139, 92, 246, 0.1));
  border-color: #6366f1;
  transform: scale(1.05);
}

.pricing-card.featured:hover {
  transform: scale(1.05) translateY(-8px);
}

.popular-badge, .best-value-badge {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  color: white;
  padding: 0.5rem 1.5rem;
  border-radius: 2rem;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.best-value-badge {
  background: linear-gradient(135deg, #f59e0b, #f97316);
}

.pricing-header {
  text-align: center;
  margin-bottom: 2rem;
  padding-bottom: 2rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}

.pricing-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  margin-bottom: 1rem;
}

.pricing-price {
  display: flex;
  align-items: flex-start;
  justify-content: center;
  color: white;
}

.currency {
  font-size: 1.5rem;
  margin-top: 0.5rem;
}

.amount {
  font-size: 4rem;
  font-weight: 800;
  line-height: 1;
}

.period {
  font-size: 1rem;
  color: rgba(255, 255, 255, 0.6);
  margin-top: 1.5rem;
}

.savings {
  margin-top: 0.5rem;
  color: #10b981;
  font-weight: 600;
  font-size: 0.875rem;
}

.pricing-features {
  list-style: none;
  padding: 0;
  margin: 0 0 2rem 0;
}

.pricing-features li {
  color: rgba(255, 255, 255, 0.8);
  padding: 0.75rem 0;
  border-bottom: 1px solid rgba(255, 255, 255, 0.05);
  font-size: 0.95rem;
}

.pricing-features li:last-child {
  border-bottom: none;
}

.pricing-button {
  width: 100%;
  padding: 1rem;
  background: rgba(99, 102, 241, 0.2);
  color: white;
  border: 2px solid #6366f1;
  border-radius: 0.75rem;
  font-weight: 700;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.pricing-button:hover {
  background: #6366f1;
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
}

.pricing-button.featured {
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  border: none;
}

.pricing-button.featured:hover {
  box-shadow: 0 15px 40px rgba(99, 102, 241, 0.6);
}

.payment-method {
  background: rgba(255, 255, 255, 0.05);
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  color: rgba(255, 255, 255, 0.8);
  font-size: 0.9rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
}

.guarantee-box {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  background: rgba(16, 185, 129, 0.1);
  border: 2px solid rgba(16, 185, 129, 0.3);
  border-radius: 1rem;
  padding: 1.5rem;
}

.guarantee-icon {
  font-size: 3rem;
  flex-shrink: 0;
}

.guarantee-title {
  font-size: 1.25rem;
  font-weight: 700;
  color: #10b981;
  margin-bottom: 0.5rem;
}

.guarantee-text {
  color: rgba(255, 255, 255, 0.7);
  line-height: 1.6;
}

@media (max-width: 768px) {
  .pricing-card.featured {
    transform: scale(1);
  }

  .pricing-card.featured:hover {
    transform: translateY(-8px);
  }
}
</style>
