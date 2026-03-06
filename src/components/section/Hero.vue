<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
</script>

<template>
  <section
    id="home"
    class="relative min-h-screen flex items-center overflow-hidden bg-white py-10 md:py-6"
  >
    <!-- Background Accent -->
    <div
      class="absolute -top-32 -right-32 w-72 md:w-96 h-72 md:h-96 bg-pink-300 blur-3xl opacity-30"
    ></div>
    <div
      class="absolute bottom-0 -right-32 w-72 md:w-96 h-72 md:h-96 bg-cyan-300 blur-3xl opacity-30"
    ></div>

    <div
      class="relative z-10 max-w-6xl mx-auto px-6 grid grid-cols-1 lg:grid-cols-2 gap-12 lg:gap-20 items-center"
    >
      <!-- LEFT -->
      <div class="text-center lg:text-left">
        <div
          class="flex items-center justify-center lg:justify-start gap-3 mb-6"
        >
          <div class="w-12 h-[2px] bg-indigo-600"></div>
          <p class="text-md uppercase tracking-widest text-slate-500">
            Fullstack Web Developer
          </p>
        </div>

        <h1 class="text-3xl md:text-5xl font-bold text-slate-900 leading-tight">
          Hi, I'm Gana — <br />
          I build fast, modern web solutions.
        </h1>

        <p
          class="mt-6 text-base md:text-lg text-slate-600 max-w-xl mx-auto lg:mx-0 leading-relaxed"
        >
          I help startups and small businesses launch modern landing pages and
          scalable web applications quickly — with clean code, clear
          communication, and no unnecessary complexity.
        </p>

        <p class="mt-6 text-sm text-slate-500">
          🚀 Fast delivery • 💬 Clear communication • 🌍 Available worldwide
        </p>

        <div class="mt-10 flex flex-wrap justify-center lg:justify-start gap-4">
          <a
            href="#portfolio"
            class="px-6 py-3 bg-slate-900 text-white rounded-lg shadow hover:bg-slate-800 transition"
          >
            View Projects
          </a>

          <a
            href="https://drive.google.com/file/d/1ryjbf4DOpIZCdyxMdEouCheDOubRZxNT/view?usp=sharing"
            target="_blank"
            class="px-6 py-3 border border-slate-300 rounded-lg hover:bg-slate-100 transition"
          >
            <FontAwesomeIcon :icon="['fas', 'download']" class="mr-2" />
            Download CV
          </a>
        </div>
      </div>

      <!-- RIGHT (TETAP TAMPIL DI MOBILE) -->
      <div class="flex justify-center relative order-first lg:order-none">
        <div
          class="w-72 sm:w-80 md:w-[380px] lg:w-[420px] aspect-square rounded-2xl shadow-xl overflow-hidden border border-slate-200"
        >
          <img
            src="/img/gana1.webp"
            alt="Gana Portfolio Preview"
            class="w-full h-full object-cover hover:scale-105 transition duration-700"
            loading="lazy"
          />
        </div>
      </div>
    </div>
  </section>
</template>
