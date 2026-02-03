<template>
  <div class="min-h-screen bg-dark flex items-center justify-center px-4">
    <div class="max-w-2xl w-full text-center">
      <!-- Sold Out Icon -->
      <div class="sold-out-icon mb-8">
        <div class="icon-wrapper">
          <svg class="w-32 h-32 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 9v2m0 4h.01m-6.938 4h13.856c1.54 0 2.502-1.667 1.732-3L13.732 4c-.77-1.333-2.694-1.333-3.464 0L3.34 16c-.77 1.333.192 3 1.732 3z" />
          </svg>
        </div>
      </div>

      <!-- Content -->
      <h1 class="text-4xl md:text-5xl font-bold mb-4 text-white">
        Promoção Esgotada
      </h1>
      
      <p class="text-xl text-red-400 mb-4">
        Esta oferta especial já foi totalmente preenchida 😔
      </p>
      
      <p class="text-gray-400 mb-8 max-w-md mx-auto">
        Infelizmente todas as vagas para esta promoção exclusiva já foram ocupadas. 
        Mas não se preocupe, temos outras ofertas incríveis esperando por você!
      </p>

      <!-- Alternative Options -->
      <div class="alternative-box mb-8">
        <h3 class="text-2xl font-bold text-white mb-4">
          Ainda está disponível:
        </h3>
        <div class="grid md:grid-cols-2 gap-4">
          <div class="option-card">
            <div class="option-badge">ATIVO</div>
            <div class="option-title">Plano Mensal</div>
            <div class="option-price">R$ 49,90/mês</div>
            <ul class="option-features">
              <li>✅ 1500+ Canais</li>
              <li>✅ Qualidade HD/4K</li>
              <li>✅ Suporte 24/7</li>
            </ul>
            <router-link to="/#assinar" class="option-button">
              Ver Plano
            </router-link>
          </div>

          <div class="option-card featured">
            <div class="option-badge popular">POPULAR</div>
            <div class="option-title">Plano Trimestral</div>
            <div class="option-price">R$ 39,90/mês</div>
            <ul class="option-features">
              <li>✅ Tudo do Mensal</li>
              <li>✅ 2 Dispositivos</li>
              <li>✅ Canais Premium</li>
            </ul>
            <router-link to="/#assinar" class="option-button">
              Ver Plano
            </router-link>
          </div>
        </div>
      </div>

      <!-- Notify Me -->
      <div class="notify-box">
        <h3 class="text-xl font-bold text-white mb-2">
          Quer saber sobre futuras promoções?
        </h3>
        <p class="text-gray-400 mb-4">
          Deixe seu e-mail e seja o primeiro a saber quando lançarmos novas ofertas!
        </p>
        <div class="flex gap-2 max-w-md mx-auto">
          <input 
            type="email" 
            placeholder="seu@email.com" 
            class="notify-input"
          />
          <button class="notify-button">
            Notificar
          </button>
        </div>
      </div>

      <!-- Back Home -->
      <div class="mt-8">
        <router-link to="/" class="btn-primary inline-block">
          ← Voltar para Home
        </router-link>
      </div>
    </div>
  </div>
</template>

<script setup>
</script>

<style scoped>
.sold-out-icon {
  display: flex;
  justify-content: center;
  animation: shake 0.5s ease-in-out;
}

.icon-wrapper {
  background: rgba(239, 68, 68, 0.1);
  border-radius: 50%;
  padding: 1.5rem;
  border: 3px solid rgba(239, 68, 68, 0.3);
}

@keyframes shake {
  0%, 100% { transform: translateX(0); }
  10%, 30%, 50%, 70%, 90% { transform: translateX(-10px); }
  20%, 40%, 60%, 80% { transform: translateX(10px); }
}

.alternative-box {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1.5rem;
  padding: 2rem;
}

.option-card {
  background: rgba(255, 255, 255, 0.05);
  border: 2px solid rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  padding: 1.5rem;
  position: relative;
  transition: all 0.3s ease;
}

.option-card:hover {
  transform: translateY(-4px);
  border-color: rgba(99, 102, 241, 0.3);
}

.option-card.featured {
  border-color: #6366f1;
  background: rgba(99, 102, 241, 0.1);
}

.option-badge {
  position: absolute;
  top: -12px;
  left: 50%;
  transform: translateX(-50%);
  background: #10b981;
  color: white;
  padding: 0.25rem 1rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  font-weight: 700;
  text-transform: uppercase;
}

.option-badge.popular {
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
}

.option-title {
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  margin-bottom: 0.5rem;
  margin-top: 0.5rem;
}

.option-price {
  font-size: 2rem;
  font-weight: 800;
  color: #6366f1;
  margin-bottom: 1rem;
}

.option-features {
  list-style: none;
  padding: 0;
  margin: 0 0 1rem 0;
  text-align: left;
}

.option-features li {
  color: rgba(255, 255, 255, 0.8);
  margin-bottom: 0.5rem;
  font-size: 0.9rem;
}

.option-button {
  display: block;
  width: 100%;
  padding: 0.75rem;
  background: rgba(99, 102, 241, 0.2);
  color: white;
  border: 2px solid #6366f1;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.option-button:hover {
  background: #6366f1;
  transform: translateY(-2px);
}

.notify-box {
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 1rem;
  padding: 2rem;
}

.notify-input {
  flex: 1;
  padding: 0.75rem 1rem;
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.2);
  border-radius: 0.5rem;
  color: white;
  outline: none;
  transition: all 0.3s ease;
}

.notify-input:focus {
  border-color: #6366f1;
  background: rgba(255, 255, 255, 0.08);
}

.notify-input::placeholder {
  color: rgba(255, 255, 255, 0.4);
}

.notify-button {
  padding: 0.75rem 1.5rem;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  color: white;
  border: none;
  border-radius: 0.5rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.3s ease;
}

.notify-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
}

.btn-primary {
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 10px 30px rgba(99, 102, 241, 0.4);
}
</style>
