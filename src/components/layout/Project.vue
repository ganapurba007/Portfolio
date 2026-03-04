<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { computed } from "vue";

const props = defineProps({
  project: Object,
});

const snippet = computed(() => {
  return props.project.description?.substring(0, 200) + "...";
});
</script>

<template>
  <div
    class="group bg-white rounded-2xl border border-slate-200 shadow-sm hover:shadow-2xl hover:-translate-y-2 transition-all duration-500 overflow-hidden"
  >
    <!-- Image -->
    <div class="relative overflow-hidden">
      <img
        :src="project.image"
        :alt="project.title"
        class="w-full h-56 object-cover transition duration-700 group-hover:scale-110"
      />

      <!-- Overlay -->
      <div
        class="absolute inset-0 bg-gradient-to-t from-black/40 via-black/10 to-transparent opacity-0 group-hover:opacity-100 transition duration-500"
      ></div>
    </div>

    <div class="p-6">
      <!-- Tech Stack -->
      <div class="flex flex-wrap gap-2 mb-3">
        <span
          v-for="stack in project.stacks"
          :key="stack"
          class="text-xs bg-slate-100 text-slate-600 px-2 py-1 rounded-full font-medium"
        >
          {{ stack }}
        </span>
      </div>

      <!-- Title -->
      <h3
        class="text-lg font-semibold text-slate-900 mb-3 group-hover:text-indigo-600 transition"
      >
        {{ project.title }}
      </h3>

      <!-- Description -->
      <p class="text-sm text-slate-600 leading-relaxed text-justify">
        {{ snippet }}
      </p>

      <!-- Button -->
      <a
        :href="project.link"
        target="_blank"
        rel="noopener noreferrer"
        class="inline-flex items-center gap-2 mt-6 text-sm font-semibold text-indigo-600 hover:gap-3 transition-all"
      >
        View Case Study
        <FontAwesomeIcon icon="fa-solid fa-arrow-right" />
      </a>
    </div>
  </div>
</template>
<style scoped></style>
