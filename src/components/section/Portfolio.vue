<script setup>
import { ref, computed } from "vue";
import { projects } from "../../data/projects.json";
import Project from "../layout/Project.vue";

const initialLimit = ref(6);
const showAll = ref(false);

// Sort projects by ID descending so newest projects appear first (excluding hidden/draft projects)
const sortedProjects = computed(() => {
  return [...projects]
    .filter((project) => !project.hide)
    .sort((a, b) => b.id - a.id);
});

// Projects currently rendered on the grid (either top 6 or all)
const displayedProjects = computed(() => {
  return showAll.value
    ? sortedProjects.value
    : sortedProjects.value.slice(0, initialLimit.value);
});

const hasMoreProjects = computed(() => {
  return sortedProjects.value.length > initialLimit.value;
});

const remainingCount = computed(() => {
  return sortedProjects.value.length - initialLimit.value;
});

const toggleShowMore = () => {
  showAll.value = !showAll.value;
  // If collapsing back to 6, scroll smoothly back to the top of the portfolio section
  if (!showAll.value) {
    const portfolioEl = document.getElementById("portfolio");
    if (portfolioEl) {
      portfolioEl.scrollIntoView({ behavior: "smooth" });
    }
  }
};
</script>

<template>
  <section
    id="portfolio"
    class="relative py-20 lg:py-28 bg-slate-100/60 dark:bg-slate-900 transition-colors duration-300 overflow-hidden"
  >
    <!-- Background Glow -->
    <div
      class="absolute top-1/3 right-0 w-96 h-96 bg-amber-400/15 dark:bg-amber-500/5 blur-3xl rounded-full pointer-events-none"
    ></div>

    <!-- Container -->
    <div class="relative max-w-6xl mx-auto px-5 sm:px-8">
      <!-- HEADER -->
      <div class="text-center max-w-2xl mx-auto">
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4 shadow-xs">
          FEATURED PROJECTS
        </span>

        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
          Selected Works & Case Studies
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400 leading-relaxed">
          A curated collection of real-world web applications built for business efficiency, public administration, and seamless digital commerce.
        </p>
      </div>

      <!-- GRID (Render displayedProjects with smooth transitions) -->
      <div class="mt-14 grid gap-6 md:grid-cols-2 lg:grid-cols-3">
        <Project
          v-for="project in displayedProjects"
          :key="project.id"
          :project="project"
        />
      </div>

      <!-- LOAD MORE / SHOW LESS BUTTON -->
      <div v-if="hasMoreProjects" class="mt-14 text-center">
        <button
          @click="toggleShowMore"
          type="button"
          class="inline-flex items-center gap-2.5 px-8 py-3.5 rounded-xl border border-slate-300 dark:border-slate-700 bg-white dark:bg-slate-900 hover:bg-emerald-50 dark:hover:bg-emerald-950/50 text-slate-800 dark:text-slate-200 hover:text-emerald-600 dark:hover:text-emerald-400 font-bold text-sm shadow-sm hover:shadow-md transition-all duration-300 hover:-translate-y-0.5 active:scale-95 cursor-pointer group"
        >
          <span>{{ showAll ? 'Show Fewer Projects' : `Show More Projects (${remainingCount} More)` }}</span>
          <svg
            :class="['w-4 h-4 transition-transform duration-300 group-hover:scale-110', showAll ? 'rotate-180 text-emerald-600 dark:text-emerald-400' : 'text-emerald-500']"
            fill="none"
            stroke="currentColor"
            viewBox="0 0 24 24"
          >
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M19 9l-7 7-7-7" />
          </svg>
        </button>
      </div>
    </div>
  </section>
</template>
