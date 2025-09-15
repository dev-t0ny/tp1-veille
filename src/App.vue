<script setup>
import SplitText from "./components/TextPopover.vue";
import { ref } from "vue";

const afficherDetails = ref(false);
</script>

<template>
<header class="fixed top-0 left-0 w-full z-50 backdrop-blur-md bg-[#282828] shadow-lg">
  <nav class="flex justify-center items-center px-8 py-4">
    <ul class="flex gap-8 text-white font-medium">
      <li>
        <a 
          href="#accueil" 
          class="relative px-4 py-2 rounded-lg transition-all duration-300 hover:bg-emerald-100/20 group"
        >
          Accueil
        </a>
      </li>
      <li>
        <a 
          href="#usage" 
          class="relative px-4 py-2 rounded-lg transition-all duration-300 hover:bg-emerald-100/20 group"
        >
          Usage
        </a>
      </li>
      <li>
        <a 
          href="#description" 
          class="relative px-4 py-2 rounded-lg transition-all duration-300 hover:bg-emerald-100/20 group"
        >
          Détails
        </a>
      </li>
      <li>
        <a 
          href="#experimentation" 
          class="relative px-4 py-2 rounded-lg transition-all duration-300 hover:bg-emerald-100/20 group"
        >
          Expérimentations
        </a>
      </li>
      <li>
        <a 
          href="#avis" 
          class="relative px-4 py-2 rounded-lg transition-all duration-300 hover:bg-emerald-100/20 group"
        >
          Avis
        </a>
      </li>
    </ul>
  </nav>
</header>

  <main class="container mx-auto p-4" id="accueil">
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

    <section
      id="usage"
      class="text-white text-center mb-[25rem] pt-[10rem] mt-[40rem]"
    >
      <SplitText
        text="L'appareil que j'ai choisi?"
        class-name="text-4xl font-semibold text-center"
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

      <div
        class="flex justify-center mx-auto items-center mt-[5rem] gap-12 bg-[#232323] p-10 rounded w-4xl"
      >
        <div
          class="w-1/4 p-10 border-4 border-dashed border-gray-600 rounded-lg hover:bg-[#494949] hover:scale-110 transform transition duration-300 ease-in-out relative"
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
              <h2 class="text-md">Capteur infrarouge passif</h2>
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
          <h3 class="text-lg font-semibold mb-2 underline underline-offset-3">
            Usage proposé
          </h3>
          <ul class="list-none text-gray-300">
            <li>
              Calculer la vitesse d'une personne ou d'un objet en mouvement.
            </li>
            <li>
              <img src="/img/animation.gif" class="mt-5" />
            </li>
          </ul>
        </div>
      </div>
    </section>

    <section
      id="description"
      class="text-white text-center mb-[25rem] pt-[10rem] mt-[5rem]"
    >
      <h2 class="text-2xl font-semibold mb-16 underline underline-offset-4">
        Description de l'objet expérimenté
      </h2>

      <div class="grid grid-cols-3 gap-8 justify-items-center">
        <div class="bg-[#232323] p-6 rounded-lg w-full max-w-md text-left">
          <h3
            class="text-md font-semibold mb-2 bg-[#353535] p-3 text-center rounded"
          >
            Résumé des fonctionnalités
          </h3>
          <blockquote
            class="p-4 my-4 border-s-4 border-green-500 bg-green-900 opacity-80"
          >
            <p class="text-md italic font-medium leading-relaxed text-white">
              "Un détecteur infrarouge est un détecteur réagissant à un
              rayonnement infrarouge"

              <a
                class="underline block mt-3"
                href="https://fr.wikipedia.org/wiki/D%C3%A9tecteur_infrarouge"
                >Wikipedia</a
              >
            </p>
          </blockquote>
          <p class="text-gray-300 mt-10 text-justify">
            Le capteur infrarouge permet de capter la présence d’un objet. Il
            lance un signal électrique lorsqu'il le détecte. À cause de cela, la
            détection de la vitesse n'est pas supporté de base. C'est en
            combinant plusieurs de ces appareils
          </p>
        </div>

        <div class="bg-[#232323] p-6 rounded-lg w-full max-w-md text-left">
          <h3
            class="text-md font-semibold mb-2 bg-[#353535] p-3 text-center rounded"
          >
            Informations supplémentaires
          </h3>

          <h2 class="text-lg font-semibold mb-2 mt-10">Fabricant:</h2>
          <ul class="list-disc list-inside text-gray-300">
            <li>Arduino</li>
          </ul>

          <h2 class="text-lg font-semibold mb-2 mt-15">
            Autres éléments pertinents:
          </h2>
          <ul class="list-disc list-inside text-gray-300">
            <li>Type de capteur utilisé (ultrason, infrarouge, etc.)</li>
            <li>Plage de détection (ex. 0–5 m)</li>
            <li>Précision</li>
          </ul>
        </div>

        <div class="bg-[#232323] p-6 rounded-lg w-full max-w-md text-left">
          <h3
            class="text-md font-semibold mb-2 bg-[#353535] p-3 text-center rounded"
          >
            Images
          </h3>
          <figure class="max-w-lg mt-5">
            <img
              class="h-auto max-w-full rounded-lg"
              src="/img/schema.png"
              alt="image description"
            />
            <figcaption
              class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
            >
              Schéma du projet
            </figcaption>
          </figure>
          <figure class="max-w-lg mt-10">
            <img
              class="h-auto max-w-full rounded-lg"
              src="/img/schema_materiel.png"
              alt="image description"
            />
            <figcaption
              class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
            >
              Schéma matériel
            </figcaption>
          </figure>
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
