<script setup>
import SplitText from "./components/TextPopover.vue";
import { ref } from "vue";

const afficherDetails = ref(false);
</script>

<template>
  <header id="accueil">
    <nav
      class="flex justify-center mx-auto gap-8 text-white p-4 mt-5 mb-8 w-1/4"
    >
      <ul>
        <a href="#accueil" class="hover:underline">Accueil</a>
      </ul>
        <ul>
        <a href="#usage" class="hover:underline">Usage</a>
      </ul>
      <ul>
        <a href="#details" class="hover:underline">Détails</a>
      </ul>
      <ul>
        <a href="#experimentation" class="hover:underline">Expérimentations</a>
      </ul>
      <ul>
        <a href="#avis" class="hover:underline">Avis</a>
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
      <a href="#usage">
        <i
          class="pi pi-arrow-down animate-bounce text-[#b0ff61] p-5 mt-75 text-3xl hover:cursor-pointer"
        ></i>
      </a>
    </section>

    <section id="usage" class="text-white text-center mb-[25rem] mt-[20rem]">
      <SplitText
        text="L'appareil que j'ai choisi?"
        class-name="text-2xl font-semibold text-center"
        :delay="30"
        :duration="0.3"
        ease="power3.out"
        split-type="chars"
        :from="{ opacity: 0, y: 40 }"
        :to="{ opacity: 1, y: 0 }"
        :threshold="0.1"
        root-margin="-100px"
        text-align="center"
        @animation-complete="handleAnimationComplete"
      />

      <div class="flex justify-center items-center gap-12 mt-20">
        <div
          class="w-1/4 p-10 border-4 border-dashed border-gray-600 rounded-lg hover:bg-gray-800 hover:scale-110 transform transition duration-300 ease-in-out relative"
          @mouseenter="afficherDetails = true"
        >
          <p v-if="!afficherDetails">Survole moi!</p>

          <transition
            enter-active-class="transition-opacity duration-700 ease-out"
            enter-from-class="opacity-0"
            enter-to-class="opacity-100"
          >
            <div v-if="afficherDetails" class="flex flex-col items-center">
              <img
                src="/img/sensor.png"
                alt="Image de l'appareil"
                class="mb-2 rounded"
              />
              <h2 class="text-xl">Détecteur de mouvement</h2>
            </div>
          </transition>
        </div>

        <div
          class="text-left max-w-sm transition-all duration-500"
          :class="
            afficherDetails
              ? 'opacity-100 translate-y-0'
              : 'opacity-0 translate-y-4'
          "
          v-show="true"
        >
          <h3 class="text-lg font-semibold mb-2">Usage proposé</h3>
          <ul class="list-disc pl-5 text-gray-300">
            <li>
              Calculer la vitesse d'une personne ou d'un objet en mouvement.
            </li>
          </ul>
        </div>
      </div>
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
