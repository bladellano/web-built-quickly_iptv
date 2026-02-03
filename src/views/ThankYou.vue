<template>
  <div class="min-h-screen bg-dark flex items-center justify-center px-4">
    <div class="max-w-2xl w-full text-center">
      <!-- Success Animation -->
      <div class="success-icon-wrapper mb-8">
        <div class="success-checkmark">
          <svg class="checkmark" viewBox="0 0 52 52">
            <circle class="checkmark-circle" cx="26" cy="26" r="25" fill="none"/>
            <path class="checkmark-check" fill="none" d="M14.1 27.2l7.1 7.2 16.7-16.8"/>
          </svg>
        </div>
      </div>

      <!-- Content -->
      <h1 class="text-4xl md:text-5xl font-bold mb-4 bg-gradient-to-r from-primary to-purple-600 bg-clip-text text-transparent">
        Assinatura Recebida!
      </h1>
      
      <p class="text-xl text-gray-300 mb-2">
        Obrigado por escolher nosso serviço! 🎉
      </p>
      
      <p class="text-gray-400 mb-8 max-w-md mx-auto">
        Você receberá um e-mail de confirmação com todos os detalhes da sua assinatura 
        e instruções para começar a assistir em alguns minutos.
      </p>

      <!-- Info Cards -->
      <div class="grid md:grid-cols-3 gap-4 mb-8">
        <div class="info-card">
          <div class="info-icon">📧</div>
          <div class="info-title">Verifique seu E-mail</div>
          <div class="info-text">Em até 5 minutos</div>
        </div>
        <div class="info-card">
          <div class="info-icon">🔑</div>
          <div class="info-title">Dados de Acesso</div>
          <div class="info-text">Login e senha</div>
        </div>
        <div class="info-card">
          <div class="info-icon">📱</div>
          <div class="info-title">Configure</div>
          <div class="info-text">Em seus dispositivos</div>
        </div>
      </div>

      <!-- Contact Support -->
      <div class="support-box">
        <p class="text-gray-300 mb-4">
          Precisa de ajuda? Nossa equipe está disponível 24/7
        </p>
        <div class="flex gap-4 justify-center flex-wrap">
          <a href="https://wa.me/5511999999999" target="_blank" class="btn-secondary">
            💬 WhatsApp
          </a>
          <a href="mailto:suporte@iptvpremium.com" class="btn-secondary">
            📧 E-mail
          </a>
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
.success-icon-wrapper {
  display: flex;
  justify-content: center;
}

.success-checkmark {
  width: 120px;
  height: 120px;
  margin: 0 auto;
}

.checkmark {
  width: 120px;
  height: 120px;
  border-radius: 50%;
  display: block;
  stroke-width: 2;
  stroke: #10b981;
  stroke-miterlimit: 10;
  box-shadow: inset 0px 0px 0px #10b981;
  animation: fill 0.4s ease-in-out 0.4s forwards, scale 0.3s ease-in-out 0.9s both;
}

.checkmark-circle {
  stroke-dasharray: 166;
  stroke-dashoffset: 166;
  stroke-width: 2;
  stroke-miterlimit: 10;
  stroke: #10b981;
  fill: none;
  animation: stroke 0.6s cubic-bezier(0.65, 0, 0.45, 1) forwards;
}

.checkmark-check {
  transform-origin: 50% 50%;
  stroke-dasharray: 48;
  stroke-dashoffset: 48;
  animation: stroke 0.3s cubic-bezier(0.65, 0, 0.45, 1) 0.8s forwards;
}

@keyframes stroke {
  100% {
    stroke-dashoffset: 0;
  }
}

@keyframes scale {
  0%, 100% {
    transform: none;
  }
  50% {
    transform: scale3d(1.1, 1.1, 1);
  }
}

@keyframes fill {
  100% {
    box-shadow: inset 0px 0px 0px 60px rgba(16, 185, 129, 0.2);
  }
}

.info-card {
  background: rgba(255, 255, 255, 0.03);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
  padding: 1.5rem;
  transition: all 0.3s ease;
}

.info-card:hover {
  background: rgba(99, 102, 241, 0.1);
  border-color: rgba(99, 102, 241, 0.3);
  transform: translateY(-4px);
}

.info-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.info-title {
  font-weight: 700;
  color: white;
  margin-bottom: 0.25rem;
}

.info-text {
  font-size: 0.875rem;
  color: rgba(255, 255, 255, 0.6);
}

.support-box {
  background: rgba(99, 102, 241, 0.1);
  border: 1px solid rgba(99, 102, 241, 0.3);
  border-radius: 1rem;
  padding: 2rem;
}

.btn-secondary {
  background: rgba(255, 255, 255, 0.1);
  color: white;
  padding: 0.75rem 1.5rem;
  border-radius: 0.5rem;
  text-decoration: none;
  font-weight: 600;
  transition: all 0.3s ease;
  display: inline-block;
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.btn-secondary:hover {
  background: rgba(255, 255, 255, 0.15);
  border-color: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
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
