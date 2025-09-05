<script setup>
import FadeContent from "./components/FadeContent.vue";
</script>

<template>
  <header>
    <nav class="flex justify-center mx-auto gap-8 text-white p-4 mt-5 mb-8 w-1/5">
      <ul>
        <a href="#about" class="hover:underline">Accueil</a>
      </ul>
      <ul>
        <a href="#projects" class="hover:underline"
          >Détails de l'appareil</a
        > 
      </ul>
      <ul>
        <a href="#contact" class="hover:underline">Avis</a>
      </ul>
    </nav>
  </header>

  <main class="container mx-auto p-4">
      <section class="text-center text-white mb-16 mt-50">
        <h1 class="text-4xl font-light mb-2">TP1 - Veille technologique</h1>
        <h2 class="text-2xl text-gray-400">
          Présenté par
          <em class="gradient-text"> Antoine Boudreau</em>
        </h2>
        <a href="">
            <i class="pi pi-arrow-down animate-bounce text-[#b0ff61] p-5 mt-75 text-3xl hover:cursor-pointer"></i>
        </a>
      </section>
  </main>
</template>

<style scoped>
@keyframes gradient {
  0% {
    background-position: 0% 50%;
  }
  50% {
    background-position: 100% 50%;
  }
  100% {
    background-position: 0% 50%;
  }
}

.gradient-text {
  background-image: linear-gradient(to right, #d1ff54, #b0ff61, #6efaee);
  background-size: 200% 100%;
  background-clip: text;
  color: transparent;
  animation: gradient 5s linear infinite;
}
</style>
