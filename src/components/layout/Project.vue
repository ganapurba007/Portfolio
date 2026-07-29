<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { computed } from "vue";

const props = defineProps({
  project: Object,
});

const snippet = computed(() => {
  return props.project.description?.substring(0, 160) + "...";
});
</script>

<template>
  <div
    class="group flex flex-col bg-slate-50/50 dark:bg-slate-800/60 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs hover:shadow-xl hover:border-emerald-500/40 hover:-translate-y-1.5 transition-all duration-300 overflow-hidden"
  >
    <!-- Image Preview Container -->
    <div class="relative overflow-hidden aspect-video bg-slate-100 dark:bg-slate-900">
      <img
        loading="lazy"
        :src="project.image"
        :alt="project.title"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-105"
      />

      <!-- Subtle Dark Overlay -->
      <div
        class="absolute inset-0 bg-slate-950/20 opacity-0 group-hover:opacity-100 transition-opacity duration-300"
      ></div>
    </div>

    <!-- Content -->
    <div class="flex flex-col flex-1 p-5">
      <!-- Tech Stacks -->
      <div class="flex flex-wrap gap-1.5 mb-3">
        <span
          v-for="stack in project.stacks"
          :key="stack"
          class="text-[11px] font-semibold px-2.5 py-0.5 rounded-full bg-emerald-50 dark:bg-emerald-950/60 text-emerald-700 dark:text-emerald-300 border border-emerald-200/50 dark:border-emerald-800/50"
        >
          {{ stack }}
        </span>
      </div>

      <!-- Title -->
      <h3
        class="text-lg font-bold text-slate-900 dark:text-white mb-2 group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors"
      >
        {{ project.title }}
      </h3>

      <!-- Description -->
      <p
        class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 leading-relaxed flex-1"
      >
        {{ snippet }}
      </p>

      <!-- Action Button -->
      <div class="mt-5 pt-4 border-t border-slate-200/60 dark:border-slate-700/60">
        <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-2 text-xs font-bold text-emerald-600 dark:text-emerald-400 hover:text-emerald-700 dark:hover:text-emerald-300 transition-all group/link"
        >
          <span>View Live Project</span>
          <svg class="w-3.5 h-3.5 group-hover/link:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
          </svg>
        </a>
      </div>
    </div>
  </div>
</template>
