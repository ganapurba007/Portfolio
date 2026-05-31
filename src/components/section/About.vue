<script setup></script>

<template>
  <section
    id="about"
    class="relative py-24 lg:py-32 bg-slate-50 dark:bg-slate-900 overflow-hidden"
  >
    <!-- Background Blur -->
    <div
      class="absolute -bottom-40 -left-40 w-[30rem] h-[30rem] bg-indigo-500/10 blur-3xl rounded-full"
    ></div>

    <div
      class="absolute -top-40 -right-40 w-[30rem] h-[30rem] bg-orange-500/10 blur-3xl rounded-full"
    ></div>

    <div class="relative z-10 max-w-7xl mx-auto px-6 lg:px-8">
      <div class="max-w-4xl mx-auto text-center">
        <!-- Label -->
        <div class="flex items-center justify-center gap-3 mb-6">
          <div class="w-12 h-[2px] bg-indigo-600"></div>

          <span
            class="uppercase tracking-[0.3em] text-xs font-semibold text-slate-500 dark:text-slate-400"
          >
            About Me
          </span>

          <div class="w-12 h-[2px] bg-indigo-600"></div>
        </div>

        <!-- Heading -->
        <h2
          class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight text-slate-900 dark:text-white"
        >
          Building Digital Solutions

          <span
            class="block mt-2 bg-gradient-to-r from-indigo-600 via-violet-600 to-cyan-500 bg-clip-text text-transparent"
          >
            That Create Real Impact
          </span>
        </h2>

        <!-- Description -->
        <p
          class="mt-8 text-lg md:text-xl leading-relaxed text-slate-600 dark:text-slate-400"
        >
          I am a
          <span class="font-semibold text-indigo-600">
            Fullstack Web Developer
          </span>
          with experience in developing business applications, information
          systems, and digital platforms that help organizations improve
          efficiency, productivity, and user engagement.
        </p>

        <p
          class="mt-5 text-lg leading-relaxed text-slate-600 dark:text-slate-400"
        >
          Beyond coding, I enjoy solving complex problems, collaborating with
          teams, and continuously learning new technologies to build scalable,
          reliable, and impactful digital solutions.
        </p>
      </div>

      <!-- Stats -->
      <div
        class="grid grid-cols-2 lg:grid-cols-4 gap-5 mt-16 max-w-5xl mx-auto"
      >
        <div
          class="group bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 rounded-3xl p-6 text-center shadow-sm hover:shadow-xl hover:-translate-y-2 transition-all duration-300"
        >
          <h3
            class="text-4xl font-bold text-indigo-600 group-hover:scale-110 transition"
          >
            2+
          </h3>

          <p class="mt-2 text-sm text-slate-500 dark:text-slate-400">
            Years Experience
          </p>
        </div>

        <div
          class="group bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 rounded-3xl p-6 text-center shadow-sm hover:shadow-xl hover:-translate-y-2 transition-all duration-300"
        >
          <h3
            class="text-4xl font-bold text-indigo-600 group-hover:scale-110 transition"
          >
            10+
          </h3>

          <p class="mt-2 text-sm text-slate-500 dark:text-slate-400">
            Completed Projects
          </p>
        </div>

        <div
          class="group bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 rounded-3xl p-6 text-center shadow-sm hover:shadow-xl hover:-translate-y-2 transition-all duration-300"
        >
          <h3
            class="text-4xl font-bold text-indigo-600 group-hover:scale-110 transition"
          >
            4+
          </h3>

          <p class="mt-2 text-sm text-slate-500 dark:text-slate-400">
            Technical Skills
          </p>
        </div>

        <div
          class="group bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 rounded-3xl p-6 text-center shadow-sm hover:shadow-xl hover:-translate-y-2 transition-all duration-300"
        >
          <h3
            class="text-4xl font-bold text-indigo-600 group-hover:scale-110 transition"
          >
            100%
          </h3>

          <p class="mt-2 text-sm text-slate-500 dark:text-slate-400">
            Commitment
          </p>
        </div>
      </div>
    </div>
  </section>
</template>
