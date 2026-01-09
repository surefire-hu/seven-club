<script setup>
import Navbar from './components/Navbar.vue'
import Hero from './components/Hero.vue'
import EventsGrid from './components/EventsGrid.vue'
import Gallery from './components/Gallery.vue'
import BookingSection from './components/BookingForm.vue'
import WhatsAppFloat from './components/WhatsAppFloat.vue'
</script>

<template>
  <div class="bg-black text-white min-h-screen selection:bg-purple-600 selection:text-white">
    <Navbar />
    
    <main>
      <Hero />
      
      <section class="py-20 text-center px-6">
        <p class="text-zinc-400 italic text-xl md:text-2xl max-w-2xl mx-auto leading-relaxed font-light">
          "Il tempio della musica a Campi Bisenzio. Luci, beat e un'esperienza sensoriale unica tutti giorni."
        </p>
      </section>

      <EventsGrid />
      <Gallery />
      <BookingSection />
    </main>

    <footer id="footer" class="bg-zinc-950 pt-20 pb-10 px-6 border-t border-white/5">
      <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-12 mb-16">
        <div>
          <div class="text-2xl font-black italic mb-6 uppercase">Seven<span class="text-purple-600">Club</span></div>
          <p class="text-zinc-500 text-sm leading-relaxed">Il punto di riferimento per la nightlife. Qualità, musica e innovazione.</p>
        </div>
        <div>
          <h4 class="font-bold uppercase tracking-widest text-xs mb-6 text-purple-500">Contatti</h4>
          <ul class="text-zinc-400 text-sm space-y-2">
            <li>Via dei Confini, 162, 50013 Campi Bisenzio FI</li>
            <li>+39 344 442 2552</li>
            <li>info@sevenclub.it</li>
          </ul>
        </div>
        <div>
          <h4 class="font-bold uppercase tracking-widest text-xs mb-6 text-purple-500">Orari</h4>
          <ul class="text-zinc-400 text-sm space-y-2">
            <li>Tutti i giorni: 23:30 - 05:00</li>
          </ul>
        </div>
        <div class="w-full h-full min-h-200px overflow-hidden rounded-lg border border-white/10">
        <iframe
          src="https://www.google.com/maps?q=Via%20dei%20Confini%2C%20162%2C%2050013%20Campi%20Bisenzio%20FI&output=embed"
          class="w-full h-full grayscale-[1] invert-[0.9] opacity-70 hover:opacity-100 transition-opacity duration-500"
          style="border:0;"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade">
        </iframe>
      </div>
      </div>
      <div class="text-center text-[10px] text-white uppercase tracking-[0.5em] border-t border-white/5 pt-10">
        © 2026 SEVEN CLUB | Designed by <a href="https://steven-hu.netlify.app/" class="text-purple-500">surefire</a>
      </div>
    </footer>

    <WhatsAppFloat />
  </div>
</template>

<style>
html {
  scroll-behavior: smooth;
}
</style>