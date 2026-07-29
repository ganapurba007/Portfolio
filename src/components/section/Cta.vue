<script setup></script>

<template>
  <section
    id="cta"
    class="py-16 sm:py-20 bg-white dark:bg-slate-900 transition-colors duration-300"
  >
    <div class="max-w-5xl mx-auto px-5 sm:px-8">
      <div
        class="relative overflow-hidden rounded-3xl bg-slate-900 dark:bg-slate-950 p-8 sm:p-12 lg:p-14 text-center text-white border border-slate-800 shadow-2xl"
      >
        <!-- Background Soft Glow -->
        <div class="absolute -top-24 -right-24 w-72 h-72 bg-emerald-500/20 blur-3xl rounded-full pointer-events-none"></div>
        <div class="absolute -bottom-24 -left-24 w-72 h-72 bg-amber-500/15 blur-3xl rounded-full pointer-events-none"></div>

        <div class="relative z-10 max-w-3xl mx-auto">
          <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-400 bg-emerald-950/80 px-3.5 py-1 rounded-full border border-emerald-800/80 mb-4">
            START A PROJECT
          </span>

          <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold leading-tight">
            Have a Project in Mind or Need an Experienced Web Developer?
          </h2>

          <p
            class="mt-4 text-base sm:text-lg text-slate-300 leading-relaxed max-w-2xl mx-auto"
          >
            Let's discuss your requirements. I'm ready to help bring your high-performance web application to life.
          </p>

          <div class="mt-8 flex justify-center gap-4 flex-wrap">
            <a
              href="#contact"
              class="px-8 py-3.5 bg-emerald-600 hover:bg-emerald-500 text-white font-semibold text-sm rounded-xl shadow-lg transition-all duration-300 hover:-translate-y-0.5 active:scale-95 flex items-center gap-2"
            >
              <span>Get in Touch</span>
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
