<script setup>
import EventCard from './EventCard.vue'

const events = [
  { id: 1, title: 'Neon Night', date: 'Ven 16 Mag', genre: 'House / Tech', image: 'https://images.unsplash.com/photo-1708449530105-ea7d453a6f89?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8NTV8fGRpc2NvdGVjYXxlbnwwfHwwfHx8Mg%3D%3D' },
  { id: 2, title: 'Deep Vibes', date: 'Sab 17 Mag', genre: 'Techno', image: 'https://images.unsplash.com/photo-1547210841-2ceb0c5f0679?w=500&auto=format&fit=crop&q=60&ixlib=rb-4.1.0&ixid=M3wxMjA3fDB8MHxzZWFyY2h8MTZ8fGRpc2NvdGVjYXxlbnwwfHwwfHx8Mg%3D%3D' },
  { id: 3, title: 'Urban Legend', date: 'Ven 23 Mag', genre: 'Hip Hop / Trap', image: 'https://images.unsplash.com/photo-1470225620780-dba8ba36b745?auto=format&fit=crop&q=80&w=800' }
]
</script>

<template>
  <section id="eventi" class="py-20 px-6 max-w-7xl mx-auto">
    <h2 class="text-4xl font-black uppercase italic mb-12 border-l-4 border-purple-600 pl-4">Prossimi Eventi</h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
      <EventCard v-for="event in events" :key="event.id" v-bind="event" />
    </div>
  </section>
</template>