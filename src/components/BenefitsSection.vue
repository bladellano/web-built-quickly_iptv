<template>
  <section id="sobre" class="section bg-dark py-24">
    <div class="section-container">
      <div class="text-center mb-16 animate-fade-in">
        <h2 class="section-title">Por que escolher nosso serviço?</h2>
        <p class="section-subtitle">
          Experiência completa de entretenimento com qualidade incomparável
        </p>
      </div>

      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
        <div 
          v-for="(benefit, index) in benefits" 
          :key="index"
          class="benefit-card group"
          :style="{ animationDelay: `${index * 0.1}s` }"
        >
          <div class="benefit-icon-wrapper">
            <div class="benefit-icon" v-html="benefit.icon"></div>
          </div>
          <h3 class="benefit-title">{{ benefit.title }}</h3>
          <p class="benefit-description">{{ benefit.description }}</p>
        </div>
      </div>

      <!-- Channel Categories -->
      <div class="mt-20">
        <h3 class="text-3xl font-bold text-center mb-12">
          Categorias Disponíveis
        </h3>
        <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-6 gap-4">
          <div 
            v-for="(category, index) in categories"
            :key="index"
            class="category-card"
          >
            <div class="category-icon">{{ category.icon }}</div>
            <div class="category-name">{{ category.name }}</div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const benefits = ref([
  {
    icon: '🎬',
    title: 'Catálogo Gigante',
    description: 'Mais de 1500 canais incluindo filmes, séries, documentários e muito mais em diversos idiomas.'
  },
  {
    icon: '📺',
    title: 'Qualidade HD/4K',
    description: 'Transmissão em alta definição com suporte a 4K para uma experiência cinematográfica.'
  },
  {
    icon: '📱',
    title: 'Multi-dispositivos',
    description: 'Assista em Smart TV, celular, tablet, computador ou qualquer dispositivo compatível.'
  },
  {
    icon: '⚡',
    title: 'Sem Travamentos',
    description: 'Servidores de alta performance garantem streaming fluido sem interrupções.'
  },
  {
    icon: '🔄',
    title: 'Atualizações Constantes',
    description: 'Lista de canais sempre atualizada com os lançamentos mais recentes.'
  },
  {
    icon: '💬',
    title: 'Suporte 24/7',
    description: 'Equipe de suporte disponível todos os dias para ajudar você quando precisar.'
  }
])

const categories = ref([
  { icon: '🎬', name: 'Filmes' },
  { icon: '📺', name: 'Séries' },
  { icon: '⚽', name: 'Esportes' },
  { icon: '📰', name: 'Notícias' },
  { icon: '🎵', name: 'Música' },
  { icon: '🎮', name: 'Infantil' },
  { icon: '🎭', name: 'Variedades' },
  { icon: '📖', name: 'Documentários' },
  { icon: '🌎', name: 'Internacional' },
  { icon: '🎪', name: 'Adultos' },
  { icon: '🏀', name: 'Premium' },
  { icon: '✨', name: 'Exclusivos' }
])
</script>

<style scoped>
.benefit-card {
  background: linear-gradient(135deg, rgba(99, 102, 241, 0.05), rgba(139, 92, 246, 0.05));
  border: 1px solid rgba(99, 102, 241, 0.1);
  border-radius: 1rem;
  padding: 2rem;
  text-align: center;
  transition: all 0.3s ease;
  opacity: 0;
  animation: fadeInUp 0.6s ease forwards;
}

.benefit-card:hover {
  transform: translateY(-8px);
  border-color: rgba(99, 102, 241, 0.3);
  box-shadow: 0 20px 40px rgba(99, 102, 241, 0.2);
}

.benefit-icon-wrapper {
  margin: 0 auto 1.5rem;
  width: 80px;
  height: 80px;
  background: linear-gradient(135deg, #6366f1, #8b5cf6);
  border-radius: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: transform 0.3s ease;
}

.benefit-card:hover .benefit-icon-wrapper {
  transform: scale(1.1) rotate(5deg);
}

.benefit-icon {
  font-size: 2.5rem;
}

.benefit-title {
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 0.75rem;
  color: white;
}

.benefit-description {
  color: rgba(255, 255, 255, 0.7);
  line-height: 1.6;
}

.category-card {
  background: rgba(255, 255, 255, 0.05);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 0.75rem;
  padding: 1.5rem;
  text-align: center;
  transition: all 0.3s ease;
  cursor: pointer;
}

.category-card:hover {
  background: rgba(99, 102, 241, 0.1);
  border-color: rgba(99, 102, 241, 0.3);
  transform: translateY(-4px);
}

.category-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.category-name {
  color: rgba(255, 255, 255, 0.9);
  font-weight: 600;
  font-size: 0.9rem;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
  from {
    opacity: 0;
    transform: translateY(20px);
  }
}
</style>
