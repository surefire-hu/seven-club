<template>
  <section id="home" class="relative h-screen w-full overflow-hidden flex items-center justify-center">
    <video 
      autoplay 
      loop 
      muted 
      playsinline
      class="absolute z-0 w-auto min-w-full min-h-full max-w-none object-cover opacity-60"
    >
      <source src="../../public/video/loop.mp4" type="video/mp4">
      Il tuo browser non supporta il video.
    </video>

    <div class="absolute inset-0 bg-linear-to-b from-black/40 via-transparent to-black z-10"></div>

    <div class="relative z-20 text-center px-4 max-w-4xl">
      <h2 class="text-purple-500 font-bold tracking-[0.4em] uppercase text-sm mb-4 animate-pulse">
        The Best Nightlife Experience
      </h2>
      <h1 class="text-6xl md:text-9xl font-black italic uppercase tracking-tighter leading-none mb-8">
        SEVEN <span class="text-transparent stroke-white" style="-webkit-text-stroke: 1px white;">CLUB</span>
      </h1>
      
      <div class="flex flex-col md:flex-row gap-4 justify-center items-center">
        <a href="#eventi" class="w-full md:w-auto bg-white text-black px-10 py-4 font-black uppercase text-sm hover:bg-purple-600 hover:text-white transition-all duration-300">
          Scopri gli Eventi
        </a>
        <a href="#prenota" class="w-full md:w-auto border border-white/50 backdrop-blur-sm px-10 py-4 font-black uppercase text-sm hover:bg-white hover:text-black transition-all duration-300">
          Prenota Tavolo
        </a>
      </div>
    </div>

    <div class="absolute bottom-10 left-1/2 -translate-x-1/2 z-20 animate-bounce md:block hidden">
      <div class="w-px h-12 bg-linear-to-b from-white to-transparent mx-auto"></div>
    </div>
  </section>
</template>

<script></script>

<style scoped>
.stroke-white {
  -webkit-text-stroke: 1px rgba(255, 255, 255, 0.5);
}
</style>