<script setup>
const phoneNumber = "393444422552"

const openWhatsApp = (type) => {
  const messages = {
    tavolo: "Ciao Seven Club, vorrei informazioni per prenotare un TAVOLO.",
    lista: "Ciao Seven Club, vorrei inserire il mio nome in LISTA."
  }
  
  const text = encodeURIComponent(messages[type])
  window.open(`https://wa.me/${phoneNumber}?text=${text}`, '_blank')
}
</script>

<template>
  <section id="prenota" class="py-24 bg-zinc-950 px-6 relative overflow-hidden">
    <div class="absolute top-0 right-0 w-64 h-64 bg-purple-600/10 blur-[100px] rounded-full"></div>
    
    <div class="max-w-5xl mx-auto relative z-10 text-center">
      <h2 class="text-4xl md:text-6xl font-black uppercase italic mb-4 tracking-tighter">
        Join the <span class="text-purple-600">Party</span>
      </h2>
      <p class="text-zinc-400 max-w-xl mx-auto mb-12 uppercase text-sm tracking-[0.2em]">
        Prenota il tuo posto in lista o riserva un tavolo esclusivo nel privé.
      </p>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
        <div class="bg-zinc-900 border border-white/5 p-10 hover:border-purple-600/50 transition-all group">
          <div class="mb-6 inline-block p-4 bg-zinc-800 group-hover:bg-purple-600 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M12 3v18"/><rect width="18" height="12" x="3" y="5" rx="2"/><path d="M3 10h18"/></svg>
          </div>
          <h3 class="text-2xl font-black uppercase mb-4">Tavoli Privé</h3>
          <p class="text-zinc-500 text-sm mb-8">Accesso prioritario, bottiglie premium e servizio al tavolo dedicato.</p>
          <button @click="openWhatsApp('tavolo')" class="w-full py-4 bg-white text-black font-black uppercase tracking-widest hover:bg-purple-600 hover:text-white transition">
            Prenota Tavolo
          </button>
        </div>

        <div class="bg-zinc-900 border border-white/5 p-10 hover:border-purple-600/50 transition-all group">
          <div class="mb-6 inline-block p-4 bg-zinc-800 group-hover:bg-purple-600 transition-colors">
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M16 21v-2a4 4 0 0 0-4-4H6a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M22 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg>
          </div>
          <h3 class="text-2xl font-black uppercase mb-4">Lista & Ticket</h3>
          <p class="text-zinc-500 text-sm mb-8">Assicurati l'ingresso ridotto entro le ore 01:00 comunicando i nomi.</p>
          <button @click="openWhatsApp('lista')" class="w-full py-4 border border-white/20 font-black uppercase tracking-widest hover:bg-white hover:text-black transition">
            Mettiti in Lista
          </button>
        </div>
      </div>

      <div class="mt-16 flex flex-wrap justify-center gap-10 opacity-50 text-[10px] font-bold uppercase tracking-[0.3em]">
        <div class="flex items-center gap-2">
          <span class="w-2 h-2 bg-purple-600 rounded-full"></span>
          Ingresso 18+
        </div>
      </div>
    </div>
  </section>
</template>