<script setup>
import { projects } from "../../data/projects.json";
import Project from "../layout/Project.vue";
</script>

<template>
  <section
    id="portfolio"
    class="relative py-20 lg:py-28 bg-white dark:bg-slate-900 transition-colors duration-300 overflow-hidden"
  >
    <!-- Background Glow -->
    <div
      class="absolute top-1/3 right-0 w-96 h-96 bg-amber-500/5 blur-3xl rounded-full pointer-events-none"
    ></div>

    <!-- Container -->
    <div class="relative max-w-6xl mx-auto px-5 sm:px-8">
      <!-- HEADER -->
      <div class="text-center max-w-2xl mx-auto">
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4">
          FEATURED PROJECTS
        </span>

        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
          Selected Works & Case Studies
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400 leading-relaxed">
          A curated collection of real-world web applications built for business efficiency, public administration, and seamless digital commerce.
        </p>
      </div>

      <!-- GRID -->
      <div class="mt-14 grid gap-6 md:grid-cols-2 lg:grid-cols-3">
        <Project
          v-for="project in projects"
          :key="project.id"
          :project="project"
        />
      </div>
    </div>
  </section>
</template>
