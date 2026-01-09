<script setup>
defineProps(['title', 'date', 'genre', 'image'])
</script>

<template>
  <div class="group relative overflow-hidden bg-zinc-900 aspect-3/4">
    <img :src="image" :alt="title" class="absolute inset-0 w-full h-full object-cover transition duration-500 group-hover:scale-110 opacity-70 group-hover:opacity-100">
    <div class="absolute inset-0 bg-linear-to-t from-black via-transparent to-transparent"></div>
    
    <div class="absolute bottom-0 p-6">
      <p class="text-purple-500 font-bold text-sm uppercase tracking-widest mb-1">{{ date }}</p>
      <h3 class="text-2xl font-black uppercase italic leading-none mb-2">{{ title }}</h3>
      <p class="text-gray-400 text-xs uppercase">{{ genre }}</p>
      <button class="mt-4 border border-white/30 px-4 py-2 text-[10px] uppercase font-bold hover:bg-white hover:text-black transition">Info & Ticket</button>
    </div>
  </div>
</template>