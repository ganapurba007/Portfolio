<script setup>
import { ref, computed } from "vue";
import { projects } from "../../data/projects.json";
import Project from "../layout/Project.vue";

const initialLimit = ref(6);
const showAll = ref(false);
const selectedFilter = ref("All");

// Filter categories
const categories = ["All", "Vue.js", "Laravel", "CodeIgniter", "Node.js"];

// Sort projects by ID descending so newest projects appear first (excluding hidden/draft projects)
const sortedProjects = computed(() => {
  return [...projects]
    .filter((project) => !project.hide)
    .sort((a, b) => b.id - a.id);
});

// Projects filtered by tech stack category
const filteredProjects = computed(() => {
  if (selectedFilter.value === "All") {
    return sortedProjects.value;
  }
  return sortedProjects.value.filter((project) =>
    project.stacks &&
    project.stacks.some(
      (stack) => stack.toLowerCase() === selectedFilter.value.toLowerCase()
    )
  );
});

// Projects currently rendered on the grid (either top 6 or all matching filter)
const displayedProjects = computed(() => {
  return showAll.value
    ? filteredProjects.value
    : filteredProjects.value.slice(0, initialLimit.value);
});

const hasMoreProjects = computed(() => {
  return filteredProjects.value.length > initialLimit.value;
});

const remainingCount = computed(() => {
  return filteredProjects.value.length - initialLimit.value;
});

const setFilter = (category) => {
  selectedFilter.value = category;
  showAll.value = false;
};

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
    <!-- Ambient Background Glows -->
    <div
      class="absolute top-1/4 -right-20 w-96 h-96 bg-emerald-500/10 dark:bg-emerald-500/5 blur-3xl rounded-full pointer-events-none"
    ></div>
    <div
      class="absolute bottom-1/4 -left-20 w-96 h-96 bg-amber-400/15 dark:bg-amber-500/5 blur-3xl rounded-full pointer-events-none"
    ></div>

    <!-- Container -->
    <div class="relative max-w-6xl mx-auto px-5 sm:px-8">
      <!-- HEADER -->
      <div class="text-center max-w-2xl mx-auto">
        <span class="inline-flex items-center gap-1.5 text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-4 py-1.5 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4 shadow-xs">
          <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 11H5m14 0a2 2 0 012 2v6a2 2 0 01-2 2H5a2 2 0 01-2-2v-6a2 2 0 012-2m14 0V9a2 2 0 00-2-2M5 11V9a2 2 0 012-2m0 0V5a2 2 0 012-2h6a2 2 0 012 2v2M7 7h10" />
          </svg>
          FEATURED PROJECTS
        </span>

        <h2 class="text-3xl sm:text-4xl lg:text-5xl font-extrabold text-slate-900 dark:text-white tracking-tight">
          Selected Works & <span class="bg-gradient-to-r from-emerald-600 to-teal-500 bg-clip-text text-transparent">Case Studies</span>
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400 leading-relaxed">
          A curated collection of real-world web applications built for business efficiency, public administration, and seamless digital commerce.
        </p>

        <!-- TECH STACK FILTER TABS -->
        <div class="mt-8 flex flex-wrap items-center justify-center gap-2">
          <button
            v-for="cat in categories"
            :key="cat"
            @click="setFilter(cat)"
            type="button"
            :class="[
              'px-4 py-2 rounded-xl text-xs sm:text-sm font-semibold transition-all duration-200 cursor-pointer',
              selectedFilter === cat
                ? 'bg-emerald-600 text-white shadow-md shadow-emerald-600/20 scale-105'
                : 'bg-white dark:bg-slate-800/80 text-slate-600 dark:text-slate-400 hover:bg-slate-100 dark:hover:bg-slate-700/60 border border-slate-200/80 dark:border-slate-700/50'
            ]"
          >
            {{ cat }}
          </button>
        </div>
      </div>

      <!-- GRID (Render displayedProjects with smooth transitions) -->
      <div v-if="filteredProjects.length > 0" class="mt-12 sm:mt-14">
        <TransitionGroup
          name="project-grid"
          tag="div"
          class="grid gap-6 md:grid-cols-2 lg:grid-cols-3"
        >
          <Project
            v-for="project in displayedProjects"
            :key="project.id"
            :project="project"
          />
        </TransitionGroup>
      </div>

      <!-- EMPTY STATE -->
      <div
        v-else
        class="mt-12 text-center py-16 px-4 rounded-2xl bg-white/60 dark:bg-slate-800/40 border border-dashed border-slate-300 dark:border-slate-700/80 max-w-md mx-auto"
      >
        <div class="w-12 h-12 mx-auto rounded-full bg-emerald-50 dark:bg-emerald-950/60 text-emerald-600 dark:text-emerald-400 flex items-center justify-center mb-3">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
          </svg>
        </div>
        <h3 class="text-base font-bold text-slate-900 dark:text-white mb-1">
          No projects found
        </h3>
        <p class="text-xs text-slate-500 dark:text-slate-400 mb-4">
          No projects match the "{{ selectedFilter }}" technology filter.
        </p>
        <button
          @click="setFilter('All')"
          type="button"
          class="inline-flex items-center gap-1.5 px-4 py-2 rounded-xl bg-emerald-600 text-white text-xs font-semibold hover:bg-emerald-500 transition-colors shadow-sm cursor-pointer"
        >
          Show All Projects
        </button>
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

<style scoped>
.project-grid-move,
.project-grid-enter-active,
.project-grid-leave-active {
  transition: all 0.35s cubic-bezier(0.4, 0, 0.2, 1);
}

.project-grid-enter-from,
.project-grid-leave-to {
  opacity: 0;
  transform: translateY(12px);
}
</style>

