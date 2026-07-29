<script setup></script>

<template>
  <section id="work" class="relative py-20 lg:py-28 bg-slate-50/90 dark:bg-slate-950 transition-colors duration-300 overflow-hidden">
    <!-- Background Glow -->
    <div
      class="absolute top-1/2 left-0 -translate-y-1/2 w-80 h-80 bg-emerald-400/10 dark:bg-emerald-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>

    <div class="relative z-10 max-w-4xl mx-auto px-5 sm:px-8">
      <!-- Title -->
      <div class="text-center max-w-2xl mx-auto mb-14">
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4 shadow-xs">
          WORK EXPERIENCE
        </span>

        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
          Professional Track Record
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400">
          Hands-on experience engineering web systems that power real business operations and scale efficiency.
        </p>
      </div>

      <!-- Timeline -->
      <div class="relative mt-8">
        <!-- Vertical Line with Emerald/Teal Accent -->
        <div
          class="absolute left-3.5 sm:left-4 top-2 bottom-2 w-0.5 bg-gradient-to-b from-emerald-500 via-teal-500 to-amber-500 rounded-full"
        ></div>

        <!-- Timeline Item -->
        <div class="relative pl-10 sm:pl-12 mb-8">
          <!-- Pulse Dot -->
          <div
            class="absolute left-1.5 sm:left-2 top-3 -translate-x-1/2 w-4 h-4 rounded-full bg-emerald-500 ring-4 ring-emerald-100 dark:ring-emerald-950 shadow-sm"
          ></div>

          <!-- Card -->
          <div
            class="bg-white dark:bg-slate-900 p-6 sm:p-7 rounded-2xl border border-slate-200 dark:border-slate-800 shadow-md hover:shadow-xl transition-all"
          >
            <!-- Date & Status -->
            <div class="flex flex-wrap items-center gap-3 mb-2">
              <span class="text-xs font-semibold text-slate-500 dark:text-slate-400">
                May 2024 – Present
              </span>

              <span
                class="text-[11px] font-bold bg-emerald-50 dark:bg-emerald-950/80 text-emerald-600 dark:text-emerald-400 border border-emerald-200/60 dark:border-emerald-800/60 px-2.5 py-0.5 rounded-full"
              >
                Current Role
              </span>
            </div>

            <!-- Role & Organization (No "-" AI format) -->
            <h3
              class="text-xl font-extrabold text-slate-900 dark:text-white"
            >
              Full-Stack Web Developer
            </h3>
            <p class="text-sm font-semibold text-emerald-600 dark:text-emerald-400 mt-0.5">
              Yogya Executive School
            </p>

            <p class="text-sm text-slate-600 dark:text-slate-300 mt-4 leading-relaxed">
              Spearheaded the development of scalable web applications for internal operations and client solutions. Streamlined workflow automation, eliminated manual overhead, and authored maintainable, modular codebases built for long-term stability.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
