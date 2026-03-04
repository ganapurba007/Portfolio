<script setup>
import { projects } from "../../data/projects.json";
import Project from "../layout/Project.vue";
</script>

<template>
  <section id="portfolio" class="relative py-24 bg-slate-200 overflow-hidden">
    <!-- Background Decoration -->
    <div
      class="absolute -top-32 -left-32 w-96 h-96 bg-indigo-100 rounded-full blur-3xl opacity-40"
    ></div>
    <div
      class="absolute -bottom-32 -right-32 w-96 h-96 bg-slate-100 rounded-full blur-3xl opacity-50"
    ></div>

    <!-- Container -->
    <div class="relative max-w-6xl mx-auto px-6">
      <!-- Section Header -->
      <div class="text-center max-w-2xl mx-auto">
        <h2 class="text-4xl md:text-5xl font-bold text-slate-900 mt-3">
          Portfolio
        </h2>

        <div class="w-20 h-1 bg-indigo-600 mx-auto mt-6 rounded-full"></div>

        <p class="text-slate-500 mt-6 leading-relaxed">
          Real projects built with performance, scalability, and business goals
          in mind.
        </p>
      </div>

      <!-- Grid -->
      <div class="mt-20 grid md:grid-cols-2 xl:grid-cols-3 gap-10">
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
