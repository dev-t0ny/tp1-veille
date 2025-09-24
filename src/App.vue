<script setup>
import { ref } from "vue";

const afficherDetails = ref(false);
</script>

<template>
  <header
    class="fixed top-0 left-0 w-full z-50 backdrop-blur-md bg-[#282828] shadow-lg"
  >
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
            href="#experimentations"
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
        <em class="text-[#b0ff61]"> Antoine Boudreau</em>
      </h2>
      <a href="#usage">
        <i
          class="pi pi-arrow-down animate-bounce text-[#b0ff61] p-5 mt-75 text-3xl hover:cursor-pointer"
        ></i>
      </a>
    </section>

    <section
      id="usage"
      class="text-white text-center mb-[25rem] pt-[10rem] mt-[10rem]"
    >
      <p class="text-4xl font-semibold text-center">
        L'appareil que j'ai choisi?
      </p>

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
              <figure class="max-w-lg">
                <img
                  src="/img/sensor.png"
                  alt="Image de l'appareil"
                  class="h-auto max-w-full rounded-lg"
                />
                <figcaption
                  class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
                >
                  Capteur infrarouge passif (<a
                    href="https://www.canadarobotix.com/products/2327"
                    class="underline text-blue-300"
                    >HC-SR501</a
                  >)
                </figcaption>
              </figure>
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
        >
          <h3 class="text-xl font-semibold mb-2">
            Une hypothèse d'utilisation de matériel informatique plausible
          </h3>
          <p class="text-gray-300">
            Calculer la vitesse d'une personne ou d'un objet en mouvement.
          </p>

          <figure class="max-w-lg mt-10">
            <img
              src="/img/animation.gif"
              alt="Animation démonstrant le calcul de vitesse"
              class="h-auto max-w-full rounded-lg"
            />
            <figcaption
              class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
            >
              Démonstration du calcul de vitesse
            </figcaption>
          </figure>
        </div>
      </div>
    </section>

    <section
      id="description"
      class="text-white text-center mb-[25rem] pt-[5rem]"
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
            </p>
            <a
              class="underline block mt-3 text-blue-300"
              href="https://fr.wikipedia.org/wiki/D%C3%A9tecteur_infrarouge"
              >Wikipedia</a
            >
          </blockquote>
          <p class="text-gray-300 mt-10 text-justify">
            Le capteur infrarouge permet de capter la présence d'un objet. Il
            lance un signal électrique lorsqu'il le détecte. À cause de cela, la
            détection de la vitesse n'est pas supporté de base. C'est en
            combinant plusieurs de ces appareils qu'on peut calculer la vitesse.
          </p>
        </div>

        <div class="bg-[#232323] p-6 rounded-lg w-full max-w-md text-left">
          <h3
            class="text-md font-semibold mb-2 bg-[#353535] p-3 text-center rounded"
          >
            Fabriquant(s) et autres éléments pertinents
          </h3>

          <h2 class="text-lg font-semibold mb-2 mt-10">Fabricant:</h2>
          <ul class="list-disc list-inside text-gray-300">
            <li>Arduino / Divers fabricants de capteurs PIR</li>
          </ul>

          <h2 class="text-lg font-semibold mb-2 mt-15">
            Autres éléments pertinents:
          </h2>
          <ul class="list-disc list-inside text-gray-300">
            <li>Voltage: 4.5V - 20V</li>
            <li>Plage de détection: 0–7 mètres</li>
            <li>Angle de détection: 120°</li>
            <li>Températures maximales: -15 ~ +70</li>
          </ul>
          <a
            href="https://www.canadarobotix.com/products/2327"
            class="underline block mt-3 text-blue-300"
            >Canada robotix</a
          >
        </div>

        <div class="bg-[#232323] p-6 rounded-lg w-full max-w-md text-left">
          <h3
            class="text-md font-semibold mb-2 bg-[#353535] p-3 text-center rounded"
          >
            Schématisation matérielle
          </h3>
          <figure class="max-w-lg mt-5">
            <img
              class="h-auto max-w-full rounded-lg"
              src="/img/schema.png"
              alt="schéma du projet"
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
              alt="schéma du matériel"
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

    <section
      id="experimentations"
      class="text-white text-center mb-[25rem] pt-[5rem]"
    >
      <h2 class="text-2xl font-semibold mb-16 underline underline-offset-4">
        Expérimentations
      </h2>

      <div
        class="bg-[#232323] p-6 rounded-xl max-w-4xl mx-auto mb-20 border border-gray-600/20"
      >
        <h3
          class="text-md font-semibold mb-6 bg-[#353535] p-3 text-center rounded"
        >
          Avant de tester...
        </h3>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
          <div class="text-left">
            <p class="text-gray-300 text-justify">
              Étant donné que Gabriel était en expérimentation avec son
              installation de Arch Linux durant le cours, il fallait trouver
              toute les dépendances pour faire fonctionner le programme de
              Arduino...
            </p>
          </div>
          <div class="flex flex-col items-center space-y-4 mt-auto mb-auto">
            <figure class="w-1/2 mx-auto">
              <img
                src="/img/experimentation1.png"
                alt="Configuration Linux"
                class="h-auto max-w-full rounded-lg"
              />
              <figcaption
                class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
              >
                I use Arch
                <a
                  href="https://knowyourmeme.com/memes/btw-i-use-arch"
                  class="underline text-blue-200"
                  >BTW</a
                >
              </figcaption>
            </figure>
          </div>
        </div>
      </div>

      <div class="space-y-32">
        <div
          class="bg-[#232323] p-8 rounded-xl max-w-5xl mx-auto shadow-2xl border border-gray-700/30"
        >
          <h3
            class="text-md font-semibold mb-8 bg-[#353535] p-3 text-center rounded"
          >
            Expérimentation #1: Test de distance optimale
          </h3>

          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-start">
            <div class="text-left space-y-6 mt-auto mb-auto">
              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Objectif:
                </h4>
                <p class="text-gray-300">
                  Déterminer la distance de détection maximale du capteur PIR
                </p>
              </div>

              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Description du contexte de réalisation:
                </h4>
                <p class="text-gray-300 text-justify">
                  Configuration avec un seul capteur PIR connecté à l'Arduino
                  Uno. Tests effectués en intérieur avec différentes distances
                  (0.5m, 1m, 2m, 3m, 5m, 7m). Le programme lancé était très
                  simple, et ne fesait que print un mot lorsqu'un signal était
                  envoyé
                </p>
              </div>

              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Résultat de l'expérimentation:
                </h4>
                <p class="text-gray-300">
                  Détection moyennement fiable, mais stable peu importe la
                  distance, soit jusqu'à 5m et un peu plus. Parfois, aucune
                  détection n'est faite alors qu'on repasse devant l'appareil
                  plusieurs fois.
                </p>
              </div>
            </div>

            <div class="flex flex-col items-center space-y-4 mt-auto mb-auto">
              <figure class="w-1/2 mx-auto">
                <img
                  src="/img/experimentation2.png"
                  alt="Test de distance du capteur PIR"
                  class="h-auto max-w-full rounded-lg"
                />
                <figcaption
                  class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
                >
                  Configuration de test pour la validation des distances
                </figcaption>
              </figure>
            </div>
          </div>
        </div>

        <div
          class="bg-[#232323] p-8 rounded-xl max-w-5xl mx-auto shadow-2xl border border-gray-700/30"
        >
          <h3
            class="text-md font-semibold mb-8 bg-[#353535] p-3 text-center rounded"
          >
            Expérimentation #2: Calcul de vitesse avec deux capteurs
          </h3>

          <div class="grid grid-cols-1 lg:grid-cols-2 gap-8 items-start">
            <div class="text-left space-y-6">
              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Objectif:
                </h4>
                <p class="text-gray-300">
                  Valider la possibilité de calculer la vitesse d'un objet en
                  mouvement en utilisant deux capteurs PIR espacés et améliorer
                  la précision du calcul.
                </p>
              </div>

              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Description du contexte de réalisation:
                </h4>
                <p class="text-gray-300 text-justify">
                  Installation de deux capteurs distants de 1 mètre (environ)
                  sur la table. Le programme mis sur le arduino sert à mesurer
                  le délai entre les deux détections. Tests avec différentes
                  vitesses de passage (marche lente ~0.5 m/s, marche normale ~1
                  m/s, course légère ~2 m/s). Validation par chronométrage
                  manuel.
                </p>
              </div>

              <div>
                <h4 class="text-lg font-semibold mb-2 text-[#b0ff61]">
                  Résultat de l'expérimentation:
                </h4>
                <p class="text-gray-300">
                  Calcul de vitesse fonctionnel avec une précision acceptable.
                  Le capteur à un peu de difficulté lors des vitesses plus
                  rapides, car il ne capte pas le mouvement à chaque fois.
                  Toutefois, lorqsue la capture du mouvement fonctionne, les
                  valeurs sembles êtres précises.
                </p>
              </div>
            </div>

            <div class="flex flex-col items-center space-y-4 mt-auto mb-auto">
              <figure class="w-1/2 mx-auto">
                <img
                  src="/img/experimentation3.png"
                  alt="Configuration double capteur pour calcul de vitesse"
                  class="h-auto w-full rounded-lg"
                />
                <figcaption
                  class="mt-2 text-sm text-center text-gray-500 dark:text-gray-400"
                >
                  Setup avec deux capteurs pour la mesure de vitesse
                </figcaption>
              </figure>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="avis" class="text-white text-center mb-[10rem] pt-[5rem]">
      <h2 class="text-2xl font-semibold mb-16 underline underline-offset-4">
        Avis
      </h2>

      <div class="max-w-6xl mx-auto space-y-12">
        <div class="bg-[#232323] p-8 rounded-lg">
          <h3 class="text-xl font-semibold mb-8 bg-[#353535] p-4 rounded">
            Avis sur la technologie
          </h3>

          <div
            class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 text-left"
          >
            <div class="bg-[#1a1a1a] p-6 rounded-lg">
              <h4 class="text-lg font-semibold mb-3 text-[#ff6161]">
                Longévité
              </h4>
              <p class="text-gray-300">
                L'appareil semble définitivement perdre en précision au fil du
                temps. Étant donné que les capteurs du cégep sont plutôt
                anciens, on commence déjà à voir certaines pertes.
              </p>
            </div>

            <div class="bg-[#1a1a1a] p-6 rounded-lg">
              <h4 class="text-lg font-semibold mb-3 text-[#fff761]">
                Stabilité
              </h4>
              <p class="text-gray-300">
                Moyennement stable. Il faut vraiment isoler l'objet ou la
                personne qui passe devant le capteur, sinon la détection est
                très imprécise.
              </p>
            </div>

            <div class="bg-[#1a1a1a] p-6 rounded-lg">
              <h4 class="text-lg font-semibold mb-3 text-[#fff761]">
                Efficacité
              </h4>
              <p class="text-gray-300">
                Bonne efficacité pour des applications simples. Consommation
                énergétique faible, idéal pour des petites démonstrations.
              </p>
            </div>

            <div class="bg-[#1a1a1a] p-6 rounded-lg">
              <h4 class="text-lg font-semibold mb-3 text-[#b0ff61]">
                Maintenabilité
              </h4>
              <p class="text-gray-300">
                C'est très facile à manier, que se soit du côté hardware, ou
                software. Le capteur expose des fonctions facilement utilisables
                et bien documentées.
              </p>
            </div>

            <div class="bg-[#1a1a1a] p-6 rounded-lg">
              <h4 class="text-lg font-semibold mb-3 text-[#fff761]">
                Robustesse à la manipulation
              </h4>
              <p class="text-gray-300">
                L'appareil semble plutôt fragile. Sans même avoir fais exprès,
                la petite protection sur le capteur est tombé à plusieurs
                reprises.
              </p>
            </div>
          </div>
        </div>

        <div class="bg-[#232323] p-8 rounded-lg text-left">
          <h3
            class="text-xl font-semibold mb-6 bg-[#353535] p-4 rounded text-center"
          >
            Justification du potentiel de la technologie
          </h3>

          <div class="space-y-4 text-gray-300">
            <p class="text-justify">
              Le capteur présente un potentiel intéressant pour des applications
              de mesure de vitesse dans des environnements contrôlés. Sa
              simplicité d'implémentation et son faible coût (environ 5$ par
              appareil) en font une solution attractive pour des projets
              éducatifs ou des prototypes de validation de concept.
            </p>

            <p class="text-justify">
              Cependant, ses limitations en termes de précision et de
              sensibilité environnementale limitent son utilisation pour des
              applications critiques où la fiabilité est essentielle. Je ne
              pense pas les réutiliser pour un projet de plus grande envergure.
            </p>
          </div>
        </div>

        <div class="bg-[#232323] p-8 rounded-lg">
          <h3 class="text-xl font-semibold mb-8 bg-[#353535] p-4 rounded">
            Comparaison avec d'autres technologies de détection et mesure
          </h3>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8 text-left">
            <div
              class="bg-green-900/20 p-6 rounded-lg border border-green-500/30"
            >
              <h4 class="text-lg font-semibold mb-4 text-green-400">
                Capteur PIR (HC-SR501)
              </h4>
              <ul class="space-y-2 text-gray-300 list-disc list-inside">
                <li>Très abordable (~5$ par capteur)</li>
                <li>Faible consommation énergétique</li>
                <li>Installation et utilisation super simple</li>
                <li>Lorsque l'appareil fonctionne, le délais est très court</li>
              </ul>
            </div>

            <div class="bg-red-900/20 p-6 rounded-lg border border-red-500/30">
              <h4 class="text-lg font-semibold mb-4 text-red-400">
                Limites principales
              </h4>
              <ul class="space-y-2 text-gray-300 list-disc list-inside">
                <li>Faible précision</li>
                <li>
                  Dès que l'environnement est moins contrôlé, l'appareil est
                  presque non fonctionnel
                </li>
                <li>Faible durabilité, l'appareil est super fragile</li>
              </ul>
            </div>
          </div>

          <div class="mt-8 bg-[#1a1a1a] p-6 rounded-lg">
            <h4 class="text-lg font-semibold mb-4">
              Alternatives principales :
            </h4>
            <div class="text-gray-300 space-y-4">
              <p>
                <strong>Caméra + IA :</strong> Déjà entrain d'être implémenté
                sur certaines routes en angleterre (<a
                  href="https://inshur.com/en-gb/blog/ai-speed-cameras-what-drivers-need-to-know"
                  class="text-blue-300 underline"
                  >Inshur</a
                >). Pourrait définitivement avoir un grand potentiel, mais pour
                le moment, la technologie est encore expérimentale et ses
                décisions doivent être validés par un humain.
              </p>
              <p>
                <strong>Puce RFID scannée :</strong> Semble être très
                prometteur! (<a
                  href="https://ieeexplore.ieee.org/document/7041138"
                  class="underline text-blue-300"
                  >Article ieeexplore</a
                >). Le système serait semblable à celui que j'ai testé, soit
                avec deux scanneur, et on calculerait le temps entre les deux
                scan.
              </p>
              <p>
                <strong>Radar Doppler :</strong> C'est ce que les policiers
                utilisent générallement. De ma compréhension, ce sont des ondes
                qui sont envoyés sur le véhicules et le temps de rebondissement
                est calculé. (<a
                  href="https://en.wikipedia.org/wiki/Doppler_radar"
                  class="underline text-blue-300"
                  >Wikipedia</a
                >)
              </p>
            </div>
          </div>
        </div>

        <div class="bg-[#232323] p-8 rounded-xl shadow-2xl">
          <h3 class="text-xl font-semibold mb-6 text-center">Avis final</h3>

          <div class="text-gray-300 space-y-4 text-justify max-w-4xl mx-auto">
            <p>
              Le capteur infrarouge passif représente une solution acceptable
              pour des applications prototypes et des démonstrations. Son
              rapport qualité-prix en fait un choix intéressant pour s'initier
              aux concepts de mesure de vitesse par détection de mouvement.
            </p>

            <p>
              Cependant, pour une utilisation en production ou dans des
              environnements variables, des solutions plus robustes comme
              l'utilisation de RFID ou même d'un radar Doppler seraient
              préférables, malgré leur coût supérieur.
            </p>
          </div>
        </div>
      </div>
    </section>

    <section>
      <div class="mt-8 pt-4 border-t border-gray-700">
        <h4 class="text-lg font-semibold mb-2 text-white">Références</h4>
        <ul class="text-blue-300 space-y-1 list-disc list-inside">
          <li>
            <a
              href="https://en.wikipedia.org/wiki/Passive_infrared_sensor"
              target="_blank"
              class="underline"
            >
              Wikipedia – Passive Infrared Sensor
            </a>
          </li>
          <li>
            <a
              href="https://ieeexplore.ieee.org/document/7041138"
              target="_blank"
              class="underline"
            >
              IEEE Xplore – RFID Speed Monitoring System
            </a>
          </li>
          <li>
            <a
              href="https://inshur.com/en-gb/blog/ai-speed-cameras-what-drivers-need-to-know"
              target="_blank"
              class="underline"
            >
              Inshur – AI Speed Cameras - What Drivers Need to Know
            </a>
          </li>
          <li>
            <a
              href="https://www.canadarobotix.com/products/2327"
              target="_blank"
              class="underline"
            >
              Canada Robotix – HC-SR501 PIR Motion Sensor
            </a>
          </li>
        </ul>
      </div>
    </section>
  </main>
</template>

<style scoped>
button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}
</style>
