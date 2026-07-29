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
    class="relative overflow-hidden bg-slate-50/50 dark:bg-slate-950 transition-colors duration-300 min-h-[calc(100vh-80px)] flex items-center"
  >
    <!-- Ambient Background Glows -->
    <div
      class="absolute -top-32 right-0 w-96 h-96 bg-emerald-400/10 dark:bg-emerald-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>
    <div
      class="absolute bottom-10 -left-20 w-80 h-80 bg-amber-400/10 dark:bg-amber-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>

    <div
      class="relative z-10 max-w-6xl mx-auto px-5 sm:px-8 lg:px-10 py-12 lg:py-16 grid lg:grid-cols-12 gap-12 lg:gap-8 items-center"
    >
      <!-- CONTENT -->
      <div
        :class="[
          'lg:col-span-7 text-center lg:text-left transition-all duration-1000',
          isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-8',
        ]"
      >
        <!-- Status Pill Badge -->
        <div
          class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/60 dark:border-emerald-800/60 mb-6"
        >
          <span class="relative flex h-2 w-2">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-400 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-500"></span>
          </span>
          <span class="text-xs font-semibold text-emerald-700 dark:text-emerald-300">
            Available for Projects & Remote Opportunities
          </span>
        </div>

        <!-- Heading -->
        <h1
          class="text-4xl sm:text-5xl lg:text-6xl font-extrabold leading-[1.15] tracking-tight text-slate-900 dark:text-white"
        >
          Hi, I'm Gana Purba.
          <span
            class="block mt-2 text-transparent bg-clip-text bg-gradient-to-r from-emerald-600 via-teal-600 to-amber-500 dark:from-emerald-400 dark:via-teal-300 dark:to-amber-300"
          >
            Full-Stack Web Developer
          </span>
        </h1>

        <!-- Description -->
        <p
          class="mt-6 text-base sm:text-lg text-slate-600 dark:text-slate-300 max-w-2xl mx-auto lg:mx-0 leading-relaxed font-normal"
        >
          I design and engineer high-performance web applications that deliver real business impact. From robust backend architectures to modern, intuitive user interfaces.
        </p>

        <!-- Highlights -->
        <div class="mt-8 grid grid-cols-3 gap-3 sm:gap-4 max-w-lg mx-auto lg:mx-0">
          <div class="p-3 sm:p-4 rounded-2xl bg-white dark:bg-slate-900/90 border border-slate-200/60 dark:border-slate-800 shadow-xs">
            <div class="text-xl sm:text-2xl font-bold text-emerald-600 dark:text-emerald-400">100%</div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-1">Clean Code</div>
          </div>
          <div class="p-3 sm:p-4 rounded-2xl bg-white dark:bg-slate-900/90 border border-slate-200/60 dark:border-slate-800 shadow-xs">
            <div class="text-xl sm:text-2xl font-bold text-emerald-600 dark:text-emerald-400">Fast</div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-1">Responsive UI</div>
          </div>
          <div class="p-3 sm:p-4 rounded-2xl bg-white dark:bg-slate-900/90 border border-slate-200/60 dark:border-slate-800 shadow-xs">
            <div class="text-xl sm:text-2xl font-bold text-emerald-600 dark:text-emerald-400">End-to-End</div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400 mt-1">Full-Stack Solutions</div>
          </div>
        </div>

        <!-- Action Buttons -->
        <div
          class="mt-8 flex flex-col sm:flex-row justify-center lg:justify-start gap-4"
        >
          <a
            href="#portfolio"
            class="px-7 py-3.5 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-semibold text-sm shadow-md hover:shadow-lg transition-all duration-300 hover:-translate-y-0.5 active:scale-95 flex items-center justify-center gap-2"
          >
            <span>View Selected Work</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
          </a>

          <a
            href="cv/resume.pdf"
            target="_blank"
            class="px-7 py-3.5 rounded-xl border border-slate-300 dark:border-slate-700 bg-white dark:bg-slate-900 hover:bg-slate-50 dark:hover:bg-slate-800 text-slate-700 dark:text-slate-200 font-semibold text-sm shadow-xs transition-all duration-300 hover:-translate-y-0.5 active:scale-95 flex items-center justify-center gap-2"
          >
            <FontAwesomeIcon
              :icon="['fas', 'download']"
              class="text-slate-500 dark:text-slate-400"
            />
            <span>Download Resume / CV</span>
          </a>
        </div>
      </div>

      <!-- HERO IMAGE -->
      <div class="lg:col-span-5 flex justify-center order-first lg:order-last">
        <div class="relative group">
          <!-- Soft Glow Overlay -->
          <div
            class="absolute -inset-1 bg-gradient-to-r from-emerald-500/20 to-amber-500/20 rounded-3xl blur-xl opacity-75 group-hover:opacity-100 transition duration-500"
          ></div>

          <!-- Main Image Frame -->
          <div
            class="relative w-64 sm:w-80 lg:w-[380px] aspect-square overflow-hidden rounded-3xl border border-slate-200/80 dark:border-slate-800 bg-slate-100 dark:bg-slate-800 shadow-2xl transition-transform duration-500 group-hover:scale-[1.02]"
          >
            <img
              src="/img/gana1.webp"
              alt="Gana Purba"
              class="w-full h-full object-cover transition duration-700 group-hover:scale-105"
              loading="lazy"
            />
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
