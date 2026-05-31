<script setup>
import { projects } from "../../data/projects.json";
import Project from "../layout/Project.vue";
</script>

<template>
  <section
    id="portfolio"
    class="relative py-24 overflow-hidden bg-gradient-to-b from-slate-100 via-slate-200 to-slate-100 dark:from-slate-950 dark:via-slate-900 dark:to-slate-950"
  >
    <!-- Glow background -->
    <div
      class="absolute -top-40 -left-40 w-[500px] h-[500px] bg-indigo-500/20 blur-[120px] rounded-full"
    ></div>
    <div
      class="absolute -bottom-40 -right-40 w-[500px] h-[500px] bg-slate-400/20 blur-[120px] rounded-full"
    ></div>

    <!-- Container -->
    <div class="relative max-w-6xl mx-auto px-6">
      <!-- HEADER -->
      <div class="text-center max-w-2xl mx-auto">
        <div class="flex items-center justify-center gap-4 mb-5">
          <span class="h-px w-12 bg-indigo-500/70"></span>

          <p
            class="text-xs font-semibold uppercase tracking-[0.35em] text-slate-500 dark:text-slate-400"
          >
            Portfolio
          </p>

          <span class="h-px w-12 bg-indigo-500/70"></span>
        </div>

        <h2 class="text-4xl font-bold text-slate-900 dark:text-white">
          My <span class="text-indigo-500">Projects</span>
        </h2>

        <p class="mt-5 text-slate-600 dark:text-slate-400 leading-relaxed">
          A curated collection of projects showcasing experience in building
          modern, scalable, and high-performance web applications.
        </p>
      </div>

      <!-- GRID -->
      <div class="mt-16 grid gap-8 md:grid-cols-2 xl:grid-cols-3">
        <Project
          v-for="project in projects"
          :key="project.id"
          :project="project"
        />
      </div>
    </div>
  </section>
</template>

<style scoped></style>
