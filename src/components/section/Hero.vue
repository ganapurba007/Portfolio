<script setup>
import { ref, onMounted } from "vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

const isVisible = ref(false);

onMounted(() => {
  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true;
      }
    },
    { threshold: 0.2 },
  );

  const el = document.querySelector("#home");
  if (el) observer.observe(el);
});
</script>

<template>
  <section
    id="home"
    class="relative overflow-hidden bg-white dark:bg-slate-900"
  >
    <!-- Background Blur -->
    <div
      class="absolute -top-40 -right-40 w-80 h-80 bg-pink-300 opacity-20 blur-3xl rounded-full"
    ></div>

    <div
      class="absolute bottom-0 -left-20 w-72 h-72 bg-cyan-300 opacity-20 blur-3xl rounded-full"
    ></div>

    <div
      class="relative z-10 max-w-6xl mx-auto px-5 sm:px-8 lg:px-10 py-8 md:py-12 lg:min-h-[calc(100vh-80px)] grid lg:grid-cols-2 gap-10 lg:gap-16 items-center"
    >
      <!-- FOTO -->
      <div
        class="flex justify-center order-1 lg:order-2 mt-2 sm:mt-4 lg:mt-[-110px]"
      >
        <div class="relative">
          <!-- Glow -->
          <div
            class="absolute inset-0 bg-gradient-to-tr from-indigo-500/30 to-cyan-500/30 blur-3xl rounded-full"
          ></div>

          <!-- Image -->
          <div
            class="relative w-56 sm:w-72 md:w-80 lg:w-[420px] aspect-square overflow-hidden rounded-3xl border border-slate-200 dark:border-slate-700 shadow-2xl"
          >
            <img
              src="/img/gana1.webp"
              alt="Gana Purba"
              class="w-full h-full object-cover transition duration-700 hover:scale-110"
              loading="lazy"
            />
          </div>
        </div>
      </div>

      <!-- KONTEN -->
      <div
        :class="[
          'order-2 lg:order-1 text-center lg:text-left transition-all duration-1000',
          isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-8',
        ]"
      >
        <!-- Subtitle -->
        <div
          class="flex items-center justify-center lg:justify-start gap-3 mb-5"
        >
          <div class="w-12 h-[2px] bg-indigo-600"></div>

          <p
            class="text-sm uppercase tracking-[0.3em] text-slate-500 dark:text-slate-300"
          >
            Fullstack Web Developer
          </p>
        </div>

        <!-- Heading -->
        <h1
          class="text-4xl sm:text-5xl lg:text-5xl xl:text-5xl font-extrabold leading-tight tracking-tight dark:text-white"
        >
          Hi, I'm

          <span
            class="bg-gradient-to-r from-indigo-600 via-violet-600 to-cyan-500 bg-clip-text text-transparent"
          >
            Gana Purba
          </span>

          <br />

          <span class="text-slate-900 dark:text-white">
            Fullstack Web Developer
          </span>
        </h1>

        <!-- Description -->
        <p
          class="mt-6 text-base md:text-lg lg:text-xl text-slate-600 dark:text-slate-400 max-w-2xl mx-auto lg:mx-0 leading-relaxed"
        >
          I build modern web applications that are fast, scalable, and easy to
          use. Passionate about transforming ideas into digital solutions that
          help businesses streamline processes, improve efficiency, and create
          better user experiences.
        </p>

        <!-- Value Proposition -->
        <p class="mt-5 text-sm md:text-base text-slate-500 dark:text-slate-400">
          🚀 Fast Delivery • 💬 Clear Communication • 🌍 Available Worldwide
        </p>

        <!-- Buttons -->
        <div
          class="mt-8 flex flex-col sm:flex-row justify-center lg:justify-start gap-4"
        >
          <a
            href="#portfolio"
            class="px-7 py-3 rounded-xl bg-indigo-600 text-white font-medium shadow-lg hover:bg-indigo-700 transition-all duration-300"
          >
            View Projects
          </a>

          <a
            href="cv/cv_ats_english.pdf"
            target="_blank"
            class="px-7 py-3 rounded-xl border border-slate-300 dark:border-slate-600 hover:bg-slate-100 dark:hover:bg-slate-800 transition-all duration-300 dark:text-white"
          >
            <FontAwesomeIcon
              :icon="['fas', 'download']"
              class="mr-2 dark:text-white"
            />
            Download CV
          </a>
        </div>
      </div>
    </div>
  </section>
</template>
