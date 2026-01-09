<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Autoplay } from 'swiper/modules'
import 'swiper/css'
const images = [
  'https://images.unsplash.com/photo-1516450360452-9312f5e86fc7?q=80&w=800&auto=format&fit=crop',
  'https://images.unsplash.com/photo-1687511844598-165c1fc387cc?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTh8fGRpc2NvdGVjYXxlbnwwfHwwfHx8Mg%3D%3D',
  'https://images.unsplash.com/photo-1545128485-c400e7702796?q=80&w=800&auto=format&fit=crop',
  'https://images.unsplash.com/photo-1584352841344-2c59ad7a055d?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTAzfHxkaXNjb3RlY2F8ZW58MHx8MHx8fDI%3D',
  'https://images.unsplash.com/photo-1709131407822-84a466b130c2?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTEwfHxkaXNjb3RlY2F8ZW58MHx8MHx8fDI%3D',
  'https://images.unsplash.com/photo-1622743941533-cde694bff56a?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTI1fHxkaXNjb3RlY2F8ZW58MHx8MHx8fDI%3D'
]
</script>

<template>
  <section id="gallery" class="py-20 bg-black">
    <div class="px-6 mb-12">
      <h2 class="text-4xl font-black uppercase italic tracking-tighter">
        The <span class="text-purple-600">Atmosphere</span>
      </h2>
      <p class="text-zinc-500 text-xs uppercase tracking-[0.3em] mt-2">
        Follow us on Instagram @Se7enClub
      </p>
    </div>

    <Swiper
      :modules="[Autoplay]"
      :slides-per-view="2"
      :space-between="8"
      :loop="true"
      :autoplay="{ delay: 3000 }"
      :breakpoints="{
        768: { slidesPerView: 3 },
        1024: { slidesPerView: 4 }
      }"
      class="px-2"
    >
      <SwiperSlide
        v-for="(img, index) in images"
        :key="index"
        class="relative aspect-square overflow-hidden group bg-zinc-900"
      >
        <img
          :src="img"
          alt="Club Scene"
          class="w-full h-full object-cover grayscale hover:grayscale-0 transition-all duration-700 scale-105 group-hover:scale-100 opacity-60 group-hover:opacity-100"
        />

        <div
          class="absolute inset-0 bg-purple-600/20 opacity-0 group-hover:opacity-100 transition-opacity duration-500 pointer-events-none"
        />
      </SwiperSlide>
    </Swiper>
  </section>
</template>