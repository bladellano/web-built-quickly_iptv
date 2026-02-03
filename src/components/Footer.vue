<template>
  <footer class="bg-dark-950 border-t border-gray-800">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div class="grid md:grid-cols-4 gap-8">
        <!-- Logo e descrição -->
        <div class="md:col-span-2">
          <a href="/" class="flex items-center space-x-2 mb-4">
            <div class="w-10 h-10 bg-gradient-to-br from-primary-500 to-accent-500 rounded-lg flex items-center justify-center">
              <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
                <path d="M21 3H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h5v2h8v-2h5c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 14H3V5h18v12z"/>
              </svg>
            </div>
            <span class="text-2xl font-bold gradient-text" style="font-family: 'Orbitron', sans-serif;">IPTV HIGOR.BR</span>
          </a>
          <p class="text-gray-500 max-w-md mb-6">
            O melhor serviço de IPTV do Brasil. Milhares de canais, filmes e séries na palma da sua mão, com a melhor qualidade e suporte 24 horas.
          </p>
          
          <!-- Redes sociais -->
          <div class="flex space-x-4">
            <a 
              v-for="social in socialLinks" 
              :key="social.name"
              :href="social.url" 
              target="_blank"
              rel="noopener noreferrer"
              class="w-10 h-10 bg-dark-800 rounded-lg flex items-center justify-center text-gray-400 hover:text-primary-400 hover:bg-dark-700 transition-all duration-300"
              :aria-label="social.name"
            >
              <component :is="social.icon" class="w-5 h-5" />
            </a>
          </div>
        </div>

        <!-- Links rápidos -->
        <div>
          <h4 class="text-white font-semibold mb-4">Links Rápidos</h4>
          <ul class="space-y-3">
            <li>
              <a href="#about" class="text-gray-500 hover:text-primary-400 transition-colors">
                Sobre o Serviço
              </a>
            </li>
            <li>
              <a href="#benefits" class="text-gray-500 hover:text-primary-400 transition-colors">
                Benefícios
              </a>
            </li>
            <li>
              <a href="#faq" class="text-gray-500 hover:text-primary-400 transition-colors">
                FAQ
              </a>
            </li>
            <li>
              <a href="#pricing" class="text-gray-500 hover:text-primary-400 transition-colors">
                Planos
              </a>
            </li>
          </ul>
        </div>

        <!-- Contato -->
        <div>
          <h4 class="text-white font-semibold mb-4">Contato</h4>
          <ul class="space-y-3">
            <li class="flex items-center text-gray-500">
              <svg class="w-5 h-5 mr-2 text-primary-400" fill="currentColor" viewBox="0 0 24 24">
                <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
              </svg>
              contato@iptvpremium.com
            </li>
            <li class="flex items-center text-gray-500">
              <svg class="w-5 h-5 mr-2 text-primary-400" fill="currentColor" viewBox="0 0 24 24">
                <path d="M6.62 10.79c1.44 2.83 3.76 5.14 6.59 6.59l2.2-2.2c.27-.27.67-.36 1.02-.24 1.12.37 2.33.57 3.57.57.55 0 1 .45 1 1V20c0 .55-.45 1-1 1-9.39 0-17-7.61-17-17 0-.55.45-1 1-1h3.5c.55 0 1 .45 1 1 0 1.25.2 2.45.57 3.57.11.35.03.74-.25 1.02l-2.2 2.2z"/>
              </svg>
              (11) 99999-9999
            </li>
            <li class="flex items-start text-gray-500">
              <svg class="w-5 h-5 mr-2 mt-0.5 text-primary-400" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
              </svg>
              <span>Atendimento 100% Online<br />Todo o Brasil</span>
            </li>
          </ul>
        </div>
      </div>

      <!-- Linha divisória -->
      <div class="border-t border-gray-800 mt-12 pt-8">
        <div class="flex flex-col md:flex-row justify-between items-center">
          <p class="text-gray-600 text-sm">
            © {{ currentYear }} IPTV Premium. Todos os direitos reservados.
          </p>
          <div class="flex space-x-6 mt-4 md:mt-0">
            <a href="#" class="text-gray-600 hover:text-gray-400 text-sm transition-colors">
              Termos de Uso
            </a>
            <a href="#" class="text-gray-600 hover:text-gray-400 text-sm transition-colors">
              Política de Privacidade
            </a>
          </div>
        </div>
      </div>
    </div>
  </footer>
</template>

<script setup>
import { h, computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())

// Ícones de redes sociais
const InstagramIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z' })
])

const FacebookIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z' })
])

const TelegramIcon = () => h('svg', { fill: 'currentColor', viewBox: '0 0 24 24' }, [
  h('path', { d: 'M11.944 0A12 12 0 0 0 0 12a12 12 0 0 0 12 12 12 12 0 0 0 12-12A12 12 0 0 0 12 0a12 12 0 0 0-.056 0zm4.962 7.224c.1-.002.321.023.465.14a.506.506 0 0 1 .171.325c.016.093.036.306.02.472-.18 1.898-.962 6.502-1.36 8.627-.168.9-.499 1.201-.82 1.23-.696.065-1.225-.46-1.9-.902-1.056-.693-1.653-1.124-2.678-1.8-1.185-.78-.417-1.21.258-1.91.177-.184 3.247-2.977 3.307-3.23.007-.032.014-.15-.056-.212s-.174-.041-.249-.024c-.106.024-1.793 1.14-5.061 3.345-.48.33-.913.49-1.302.48-.428-.008-1.252-.241-1.865-.44-.752-.245-1.349-.374-1.297-.789.027-.216.325-.437.893-.663 3.498-1.524 5.83-2.529 6.998-3.014 3.332-1.386 4.025-1.627 4.476-1.635z' })
])

const socialLinks = [
  { name: 'Instagram', url: 'https://instagram.com', icon: InstagramIcon },
  { name: 'Facebook', url: 'https://facebook.com', icon: FacebookIcon },
  { name: 'Telegram', url: 'https://telegram.org', icon: TelegramIcon }
]
</script>
