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
        <!-- Section Label -->
        <div class="flex items-center justify-center gap-4 mb-4">
          <span class="w-10 h-px bg-indigo-600"></span>

          <p
            class="text-xs font-semibold uppercase tracking-[0.25em] text-slate-500"
          >
            Portfolio
          </p>

          <span class="w-10 h-px bg-indigo-600"></span>
        </div>

        <!-- Title -->
        <h2 class="text-3xl md:text-4xl font-bold text-slate-900">
          My <span class="text-indigo-600">Projects</span>
        </h2>

        <!-- Description -->
        <p class="mt-4 text-slate-600 text-sm md:text-base leading-relaxed">
          A collection of projects showcasing my experience in building modern,
          scalable, and high-performance web applications.
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
