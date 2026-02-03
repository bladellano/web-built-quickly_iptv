<template>
  <nav 
    class="fixed top-0 left-0 right-0 z-50 transition-all duration-300"
    :class="isScrolled ? 'bg-dark-900/95 backdrop-blur-md shadow-lg' : 'bg-transparent'"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16 md:h-20">
        <!-- Logo -->
        <a href="/" class="flex items-center space-x-2">
          <div class="w-10 h-10 bg-gradient-to-br from-primary-500 to-accent-500 rounded-lg flex items-center justify-center">
            <svg class="w-6 h-6 text-white" fill="currentColor" viewBox="0 0 24 24">
              <path d="M21 3H3c-1.1 0-2 .9-2 2v12c0 1.1.9 2 2 2h5v2h8v-2h5c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm0 14H3V5h18v12z"/>
            </svg>
          </div>
          <span class="text-xl font-bold gradient-text">IPTV Premium</span>
        </a>

        <!-- Menu Desktop -->
        <div class="hidden md:flex items-center space-x-8">
          <a 
            v-for="item in menuItems" 
            :key="item.href"
            :href="item.href"
            class="text-gray-300 hover:text-primary-400 transition-colors duration-300 font-medium"
          >
            {{ item.label }}
          </a>
          <a 
            href="#pricing" 
            class="btn-glow px-6 py-2.5 bg-gradient-to-r from-primary-500 to-primary-600 text-white font-semibold rounded-full hover:from-primary-600 hover:to-primary-700 transition-all duration-300 transform hover:scale-105"
          >
            Assine Agora
          </a>
        </div>

        <!-- Menu Mobile Toggle -->
        <button 
          @click="toggleMobileMenu"
          class="md:hidden p-2 text-gray-300 hover:text-white transition-colors"
          aria-label="Abrir menu"
        >
          <svg v-if="!isMobileMenuOpen" class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/>
          </svg>
          <svg v-else class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"/>
          </svg>
        </button>
      </div>

      <!-- Menu Mobile -->
      <transition
        enter-active-class="transition duration-200 ease-out"
        enter-from-class="opacity-0 -translate-y-4"
        enter-to-class="opacity-100 translate-y-0"
        leave-active-class="transition duration-150 ease-in"
        leave-from-class="opacity-100 translate-y-0"
        leave-to-class="opacity-0 -translate-y-4"
      >
        <div 
          v-if="isMobileMenuOpen" 
          class="md:hidden bg-dark-900/95 backdrop-blur-md rounded-b-2xl pb-4"
        >
          <div class="flex flex-col space-y-2 px-4">
            <a 
              v-for="item in menuItems" 
              :key="item.href"
              :href="item.href"
              @click="closeMobileMenu"
              class="text-gray-300 hover:text-primary-400 transition-colors duration-300 py-3 border-b border-gray-800"
            >
              {{ item.label }}
            </a>
            <a 
              href="#pricing" 
              @click="closeMobileMenu"
              class="btn-glow mt-4 px-6 py-3 bg-gradient-to-r from-primary-500 to-primary-600 text-white font-semibold rounded-full text-center hover:from-primary-600 hover:to-primary-700 transition-all duration-300"
            >
              Assine Agora
            </a>
          </div>
        </div>
      </transition>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isScrolled = ref(false)
const isMobileMenuOpen = ref(false)

const menuItems = [
  { label: 'Sobre', href: '#about' },
  { label: 'Benefícios', href: '#benefits' },
  { label: 'FAQ', href: '#faq' },
]

const handleScroll = () => {
  isScrolled.value = window.scrollY > 50
}

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value
}

const closeMobileMenu = () => {
  isMobileMenuOpen.value = false
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>
