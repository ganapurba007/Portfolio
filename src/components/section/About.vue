<script setup></script>

<template>
  <section
    id="about"
    class="relative py-20 lg:py-28 bg-slate-100/60 dark:bg-slate-900 transition-colors duration-300 overflow-hidden"
  >
    <!-- Background Glow -->
    <div
      class="absolute top-1/2 left-0 -translate-y-1/2 w-96 h-96 bg-emerald-400/15 dark:bg-emerald-500/5 blur-3xl rounded-full pointer-events-none"
    ></div>

    <div class="relative z-10 max-w-6xl mx-auto px-5 sm:px-8">
      <div class="max-w-3xl mx-auto text-center">
        <!-- Badge -->
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4 shadow-xs">
          ABOUT ME
        </span>

        <!-- Heading -->
        <h2
          class="text-3xl sm:text-4xl lg:text-5xl font-extrabold leading-tight text-slate-900 dark:text-white"
        >
          Turning Complex Business Ideas Into High-Impact Digital Solutions
        </h2>

        <!-- Description -->
        <p
          class="mt-6 text-base sm:text-lg leading-relaxed text-slate-600 dark:text-slate-300"
        >
          I am a Full-Stack Web Developer experienced in building enterprise management systems, web applications, and secure RESTful APIs. My primary focus is on delivering intuitive user experiences backed by clean, maintainable architecture.
        </p>

        <p
          class="mt-4 text-base sm:text-lg leading-relaxed text-slate-600 dark:text-slate-300"
        >
          Beyond writing code, I enjoy solving architectural challenges, collaborating in cross-functional teams, and continuously adopting modern web practices to deliver exceptional project outcomes.
        </p>
      </div>

      <!-- Stats Cards -->
      <div
        class="grid grid-cols-2 lg:grid-cols-4 gap-4 sm:gap-6 mt-14 max-w-4xl mx-auto"
      >
        <div
          class="group bg-white dark:bg-slate-800/60 border border-slate-200/90 dark:border-slate-800 rounded-2xl p-6 text-center shadow-md hover:border-emerald-500/50 hover:shadow-xl hover:-translate-y-1 transition-all duration-300"
        >
          <div
            class="text-3xl sm:text-4xl font-extrabold text-emerald-600 dark:text-emerald-400 group-hover:scale-105 transition-transform"
          >
            2+
          </div>
          <div class="mt-2 text-xs sm:text-sm font-semibold text-slate-700 dark:text-slate-300">
            Years Experience
          </div>
        </div>

        <div
          class="group bg-white dark:bg-slate-800/60 border border-slate-200/90 dark:border-slate-800 rounded-2xl p-6 text-center shadow-md hover:border-emerald-500/50 hover:shadow-xl hover:-translate-y-1 transition-all duration-300"
        >
          <div
            class="text-3xl sm:text-4xl font-extrabold text-emerald-600 dark:text-emerald-400 group-hover:scale-105 transition-transform"
          >
            10+
          </div>
          <div class="mt-2 text-xs sm:text-sm font-semibold text-slate-700 dark:text-slate-300">
            Delivered Projects
          </div>
        </div>

        <div
          class="group bg-white dark:bg-slate-800/60 border border-slate-200/90 dark:border-slate-800 rounded-2xl p-6 text-center shadow-md hover:border-emerald-500/50 hover:shadow-xl hover:-translate-y-1 transition-all duration-300"
        >
          <div
            class="text-3xl sm:text-4xl font-extrabold text-emerald-600 dark:text-emerald-400 group-hover:scale-105 transition-transform"
          >
            Full-Stack
          </div>
          <div class="mt-2 text-xs sm:text-sm font-semibold text-slate-700 dark:text-slate-300">
            Frontend & Backend
          </div>
        </div>

        <div
          class="group bg-white dark:bg-slate-800/60 border border-slate-200/90 dark:border-slate-800 rounded-2xl p-6 text-center shadow-md hover:border-emerald-500/50 hover:shadow-xl hover:-translate-y-1 transition-all duration-300"
        >
          <div
            class="text-3xl sm:text-4xl font-extrabold text-emerald-600 dark:text-emerald-400 group-hover:scale-105 transition-transform"
          >
            100%
          </div>
          <div class="mt-2 text-xs sm:text-sm font-semibold text-slate-700 dark:text-slate-300">
            Quality Commitment
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
