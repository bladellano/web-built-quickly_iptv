<template>
  <nav 
    :class="['fixed top-0 left-0 right-0 z-50 transition-all duration-300', scrolled ? 'bg-dark/95 backdrop-blur-lg shadow-lg' : 'bg-transparent']"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-20">
        <!-- Logo -->
        <router-link to="/" class="flex items-center space-x-2">
          <div class="w-10 h-10 bg-gradient-to-br from-primary to-purple-600 rounded-lg flex items-center justify-center">
            <span class="text-2xl font-bold">TV</span>
          </div>
          <span class="text-xl font-bold bg-gradient-to-r from-primary to-purple-600 bg-clip-text text-transparent">
            IPTV Premium
          </span>
        </router-link>

        <!-- Desktop Menu -->
        <div class="hidden md:flex items-center space-x-8">
          <a 
            v-for="item in menuItems" 
            :key="item.id"
            :href="item.href"
            class="text-gray-300 hover:text-white transition-colors duration-200 font-medium"
          >
            {{ item.label }}
          </a>
          <a 
            href="#assinar" 
            class="btn-primary"
          >
            Assine Agora
          </a>
        </div>

        <!-- Mobile Menu Button -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden text-white focus:outline-none"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path 
              v-if="!mobileMenuOpen"
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M4 6h16M4 12h16M4 18h16"
            />
            <path 
              v-else
              stroke-linecap="round" 
              stroke-linejoin="round" 
              stroke-width="2" 
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>
    </div>

    <!-- Mobile Menu -->
    <transition
      enter-active-class="transition ease-out duration-200"
      enter-from-class="opacity-0 -translate-y-1"
      enter-to-class="opacity-100 translate-y-0"
      leave-active-class="transition ease-in duration-150"
      leave-from-class="opacity-100 translate-y-0"
      leave-to-class="opacity-0 -translate-y-1"
    >
      <div 
        v-if="mobileMenuOpen" 
        class="md:hidden bg-dark-lighter border-t border-gray-800"
      >
        <div class="px-4 py-6 space-y-4">
          <a 
            v-for="item in menuItems" 
            :key="item.id"
            :href="item.href"
            @click="mobileMenuOpen = false"
            class="block text-gray-300 hover:text-white transition-colors duration-200 font-medium py-2"
          >
            {{ item.label }}
          </a>
          <a 
            href="#assinar"
            @click="mobileMenuOpen = false" 
            class="block btn-primary text-center"
          >
            Assine Agora
          </a>
        </div>
      </div>
    </transition>
  </nav>
</template>

<script>
import { ref, onMounted, onUnmounted } from 'vue'

export default {
  name: 'Navbar',
  setup() {
    const scrolled = ref(false)
    const mobileMenuOpen = ref(false)

    const menuItems = [
      { id: 1, label: 'Sobre o Serviço', href: '#sobre' },
      { id: 2, label: 'Canais Disponíveis', href: '#canais' },
      { id: 3, label: 'FAQ', href: '#faq' }
    ]

    const handleScroll = () => {
      scrolled.value = window.scrollY > 50
    }

    onMounted(() => {
      window.addEventListener('scroll', handleScroll)
    })

    onUnmounted(() => {
      window.removeEventListener('scroll', handleScroll)
    })

    return {
      scrolled,
      mobileMenuOpen,
      menuItems
    }
  }
}
</script>
