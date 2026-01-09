<script setup>
import { ref, onMounted, onUnmounted, watch } from 'vue'

const isMenuOpen = ref(false)
const isScrolled = ref(false)

const checkSize = () => {
  if (window.innerWidth >= 768) isMenuOpen.value = false
}

const handleScroll = () => {
  isScrolled.value = window.scrollY > 20
}

watch(isMenuOpen, (val) => {
  document.body.style.overflow = val ? 'hidden' : 'auto'
})

onMounted(() => {
  window.addEventListener('resize', checkSize)
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkSize)
  window.removeEventListener('scroll', handleScroll)
})

const links = [
  { name: 'Home', href: '#home' },
  { name: 'Eventi', href: '#eventi' },
  { name: 'Tavoli', href: '#prenota' },
  { name: 'Contatti', href: '#footer' }
]
</script>

<template>
  <nav 
    :class="[
      'fixed top-0 left-0 w-full z-200 transition-all duration-500',
      isScrolled || isMenuOpen ? 'bg-black py-4' : 'bg-transparent py-6'
    ]"
  >
    <div class="max-w-7xl mx-auto px-6 flex justify-between items-center">
      
      <a href="#" class="relative z-210 text-2xl font-black tracking-tighter uppercase italic">
        S7VEN<span class="text-purple-600">CLUB</span>
      </a>

      <div class="hidden md:flex items-center space-x-10">
        <a 
          v-for="link in links" 
          :key="link.name" 
          :href="link.href"
          class="text-[11px] font-bold uppercase tracking-[0.3em] hover:text-purple-500 transition"
        >
          {{ link.name }}
        </a>
        <a href="#prenota" class="bg-white text-black px-6 py-2 text-[11px] font-black uppercase tracking-widest hover:bg-purple-600 hover:text-white transition">
          Prenota
        </a>
      </div>

      <button 
        @click="isMenuOpen = !isMenuOpen"
        class="relative z-210 md:hidden w-10 h-10 flex flex-col justify-center items-center gap-1.5 focus:outline-none"
      >
        <span :class="['block w-6 h-0.5 bg-white transition-transform duration-300', isMenuOpen ? 'rotate-45 translate-y-2' : '']"></span>
        <span :class="['block w-6 h-0.5 bg-white transition-opacity duration-300', isMenuOpen ? 'opacity-0' : '']"></span>
        <span :class="['block w-6 h-0.5 bg-white transition-transform duration-300', isMenuOpen ? '-rotate-45 -translate-y-2' : '']"></span>
      </button>

      <div 
        :class="[
          'fixed inset-0 bg-black flex flex-col items-center justify-center transition-all duration-500 ease-in-out md:hidden',
          isMenuOpen ? 'translate-y-0 opacity-100' : '-translate-y-full opacity-0'
        ]"
      >
        <div class="flex flex-col items-center space-y-8">
          <a 
            v-for="(link, index) in links" 
            :key="index"
            :href="link.href"
            @click="isMenuOpen = false"
            class="text-4xl font-black uppercase italic tracking-tighter hover:text-purple-600 transition"
          >
            {{ link.name }}
          </a>
          <a 
            href="#prenota" 
            @click="isMenuOpen = false"
            class="mt-4 bg-purple-600 px-10 py-4 text-sm font-black uppercase tracking-widest"
          >
            Prenota Ora
          </a>
        </div>

        <div class="absolute bottom-10 text-center">
          <p class="text-zinc-500 text-[10px] uppercase tracking-widest mb-2">Seguici</p>
          <div class="flex space-x-6 text-xs font-bold uppercase">
            <span>Instagram</span>
            <span>Facebook</span>
          </div>
        </div>
      </div>

    </div>
  </nav>
</template>