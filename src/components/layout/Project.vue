<script setup>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { ref, computed, onMounted, onBeforeUnmount } from "vue";

const props = defineProps({
  project: Object,
});

const isModalOpen = ref(false);
const currentImageIndex = ref(0);

const snippet = computed(() => {
  if (!props.project.description) return "";
  return props.project.description.length > 140
    ? props.project.description.substring(0, 140) + "..."
    : props.project.description;
});

const imageList = computed(() => {
  if (Array.isArray(props.project.images) && props.project.images.length > 0) {
    return props.project.images;
  }
  return props.project.image ? [props.project.image] : [];
});

const openModal = () => {
  currentImageIndex.value = 0;
  isModalOpen.value = true;
  document.body.style.overflow = "hidden";
};

const closeModal = () => {
  isModalOpen.value = false;
  document.body.style.overflow = "";
};

const nextImage = () => {
  if (imageList.value.length <= 1) return;
  currentImageIndex.value = (currentImageIndex.value + 1) % imageList.value.length;
};

const prevImage = () => {
  if (imageList.value.length <= 1) return;
  currentImageIndex.value = (currentImageIndex.value - 1 + imageList.value.length) % imageList.value.length;
};

const handleKeyDown = (e) => {
  if (!isModalOpen.value) return;
  if (e.key === "Escape") {
    closeModal();
  } else if (e.key === "ArrowRight") {
    nextImage();
  } else if (e.key === "ArrowLeft") {
    prevImage();
  }
};

onMounted(() => {
  window.addEventListener("keydown", handleKeyDown);
});

onBeforeUnmount(() => {
  window.removeEventListener("keydown", handleKeyDown);
  document.body.style.overflow = "";
});
</script>

<template>
  <div
    class="group flex flex-col bg-slate-50/50 dark:bg-slate-800/60 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs hover:shadow-xl hover:border-emerald-500/40 hover:-translate-y-1.5 transition-all duration-300 overflow-hidden"
  >
    <!-- Image Preview Container (Clickable to open detail modal) -->
    <div
      @click="openModal"
      class="relative overflow-hidden aspect-video bg-slate-100 dark:bg-slate-900 cursor-pointer group/img"
    >
      <img
        loading="lazy"
        :src="project.image"
        :alt="project.title"
        class="w-full h-full object-cover transition-transform duration-500 group-hover/img:scale-105"
      />

      <!-- Hover Overlay with Detail Badge -->
      <div
        class="absolute inset-0 bg-slate-950/40 opacity-0 group-hover/img:opacity-100 transition-opacity duration-300 flex items-center justify-center"
      >
        <span
          class="px-4 py-2 rounded-full bg-white/90 dark:bg-slate-900/90 backdrop-blur-md text-slate-900 dark:text-white text-xs font-bold shadow-lg transform translate-y-2 group-hover/img:translate-y-0 transition-transform duration-300 flex items-center gap-1.5"
        >
          <svg class="w-4 h-4 text-emerald-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M2.458 12C3.732 7.943 7.523 5 12 5c4.478 0 8.268 2.943 9.542 7-1.274 4.057-5.064 7-9.542 7-4.477 0-8.268-2.943-9.542-7z" />
          </svg>
          View Details
        </span>
      </div>
    </div>

    <!-- Card Content -->
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

      <!-- Title (Clickable) -->
      <h3
        @click="openModal"
        class="text-lg font-bold text-slate-900 dark:text-white mb-2 group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors cursor-pointer"
      >
        {{ project.title }}
      </h3>

      <!-- Description Snippet -->
      <p
        class="text-xs sm:text-sm text-slate-600 dark:text-slate-300 leading-relaxed flex-1"
      >
        {{ snippet }}
      </p>

      <!-- Action Buttons -->
      <div class="mt-5 pt-4 border-t border-slate-200/60 dark:border-slate-700/60 flex items-center justify-between gap-3">
        <!-- View Details Button -->
        <button
          @click="openModal"
          type="button"
          class="inline-flex items-center gap-1.5 text-xs font-bold text-slate-700 dark:text-slate-300 hover:text-emerald-600 dark:hover:text-emerald-400 transition-colors cursor-pointer"
        >
          <span>Quick Overview</span>
          <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
          </svg>
        </button>

        <!-- Direct Live Link -->
        <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          class="inline-flex items-center gap-1.5 text-xs font-bold text-emerald-600 dark:text-emerald-400 hover:text-emerald-700 dark:hover:text-emerald-300 transition-all group/link"
        >
          <span>Visit Live</span>
          <svg class="w-3.5 h-3.5 group-hover/link:translate-x-1 transition-transform" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
          </svg>
        </a>
      </div>
    </div>

    <!-- Project Detail Modal -->
    <Teleport to="body">
      <transition
        enter-active-class="transition duration-300 ease-out"
        enter-from-class="opacity-0"
        enter-to-class="opacity-100"
        leave-active-class="transition duration-200 ease-in"
        leave-from-class="opacity-100"
        leave-to-class="opacity-0"
      >
        <div
          v-if="isModalOpen"
          class="fixed inset-0 z-50 flex items-center justify-center p-3 sm:p-6 bg-slate-950/80 backdrop-blur-md"
          @click.self="closeModal"
        >
          <div
            class="relative w-full max-w-3xl bg-white dark:bg-slate-900 rounded-2xl shadow-2xl border border-slate-200/80 dark:border-slate-800 overflow-hidden flex flex-col max-h-[90vh]"
          >
            <!-- Modal Header -->
            <div class="flex items-center justify-between px-6 py-4 border-b border-slate-200 dark:border-slate-800 bg-slate-50 dark:bg-slate-950/60">
              <div class="flex items-center gap-3">
                <div class="p-2 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 text-emerald-600 dark:text-emerald-400">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
                  </svg>
                </div>
                <div>
                  <h3 class="text-base font-bold text-slate-900 dark:text-white">
                    {{ project.title }}
                  </h3>
                  <p class="text-xs text-slate-500 dark:text-slate-400">Project Overview & Gallery</p>
                </div>
              </div>

              <!-- Close Button -->
              <button
                @click="closeModal"
                type="button"
                class="p-2 rounded-xl text-slate-500 hover:text-slate-800 dark:text-slate-400 dark:hover:text-white hover:bg-slate-200/60 dark:hover:bg-slate-800 transition-colors focus:outline-none"
                aria-label="Close modal"
              >
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                </svg>
              </button>
            </div>

            <!-- Modal Content (Scrollable) -->
            <div class="flex-1 overflow-y-auto p-6 space-y-6">
              <!-- Image Carousel Container -->
              <div class="relative overflow-hidden rounded-xl border border-slate-200 dark:border-slate-800 shadow-sm bg-slate-100 dark:bg-slate-950 group/carousel">
                <div class="relative w-full aspect-video flex items-center justify-center overflow-hidden">
                  <img
                    :src="imageList[currentImageIndex]"
                    :alt="`${project.title} screenshot ${currentImageIndex + 1}`"
                    class="w-full h-full object-cover transition-opacity duration-300"
                  />
                </div>

                <!-- Slide Counter Badge (shown if multiple images) -->
                <div
                  v-if="imageList.length > 1"
                  class="absolute top-3 right-3 px-2.5 py-1 rounded-full bg-slate-950/70 backdrop-blur-md text-white text-[11px] font-semibold border border-white/10"
                >
                  {{ currentImageIndex + 1 }} / {{ imageList.length }}
                </div>

                <!-- Navigation Arrows (shown if multiple images) -->
                <template v-if="imageList.length > 1">
                  <!-- Prev Arrow -->
                  <button
                    @click.stop="prevImage"
                    type="button"
                    class="absolute left-3 top-1/2 -translate-y-1/2 p-2 rounded-full bg-slate-950/60 hover:bg-slate-950/90 text-white backdrop-blur-md transition-all opacity-80 hover:opacity-100 hover:scale-110 focus:outline-none"
                    aria-label="Previous image"
                  >
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M15 19l-7-7 7-7" />
                    </svg>
                  </button>

                  <!-- Next Arrow -->
                  <button
                    @click.stop="nextImage"
                    type="button"
                    class="absolute right-3 top-1/2 -translate-y-1/2 p-2 rounded-full bg-slate-950/60 hover:bg-slate-950/90 text-white backdrop-blur-md transition-all opacity-80 hover:opacity-100 hover:scale-110 focus:outline-none"
                    aria-label="Next image"
                  >
                    <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2.5" d="M9 5l7 7-7 7" />
                    </svg>
                  </button>

                  <!-- Indicator Dots -->
                  <div class="absolute bottom-3 left-1/2 -translate-x-1/2 flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-slate-950/60 backdrop-blur-md border border-white/10">
                    <button
                      v-for="(img, idx) in imageList"
                      :key="idx"
                      @click.stop="currentImageIndex = idx"
                      type="button"
                      :class="[
                        'w-2 h-2 rounded-full transition-all',
                        currentImageIndex === idx
                          ? 'bg-emerald-400 w-5'
                          : 'bg-white/50 hover:bg-white'
                      ]"
                      :aria-label="`Go to slide ${idx + 1}`"
                    ></button>
                  </div>
                </template>
              </div>

              <!-- Tech Stacks -->
              <div>
                <h4 class="text-xs font-semibold uppercase tracking-wider text-slate-500 dark:text-slate-400 mb-2">
                  Technologies Used
                </h4>
                <div class="flex flex-wrap gap-2">
                  <span
                    v-for="stack in project.stacks"
                    :key="stack"
                    class="text-xs font-semibold px-3 py-1 rounded-full bg-emerald-50 dark:bg-emerald-950/80 text-emerald-700 dark:text-emerald-300 border border-emerald-200/60 dark:border-emerald-800/60"
                  >
                    {{ stack }}
                  </span>
                </div>
              </div>

              <!-- Full Description -->
              <div>
                <h4 class="text-xs font-semibold uppercase tracking-wider text-slate-500 dark:text-slate-400 mb-2">
                  Project Description
                </h4>
                <p class="text-sm text-slate-700 dark:text-slate-300 leading-relaxed">
                  {{ project.description }}
                </p>
              </div>
            </div>

            <!-- Modal Footer -->
            <div class="flex items-center justify-end gap-3 px-6 py-4 border-t border-slate-200 dark:border-slate-800 bg-slate-50 dark:bg-slate-950/60">
              <button
                @click="closeModal"
                type="button"
                class="px-5 py-2.5 rounded-xl border border-slate-300 dark:border-slate-700 text-slate-700 dark:text-slate-300 font-semibold text-xs hover:bg-slate-100 dark:hover:bg-slate-800 transition-colors"
              >
                Close
              </button>

              <a
                :href="project.link"
                target="_blank"
                rel="noopener noreferrer"
                class="inline-flex items-center gap-2 px-5 py-2.5 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-semibold text-xs shadow-md transition-all active:scale-95"
              >
                <span>Visit Live Project</span>
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
                </svg>
              </a>
            </div>
          </div>
        </div>
      </transition>
    </Teleport>
  </div>
</template>
