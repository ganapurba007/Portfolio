<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

const isVisible = ref(false);
const isPreviewOpen = ref(false);

const openResumePreview = () => {
  isPreviewOpen.value = true;
  document.body.style.overflow = "hidden";
};

const closeResumePreview = () => {
  isPreviewOpen.value = false;
  document.body.style.overflow = "";
};

const handleKeyDown = (e) => {
  if (e.key === "Escape" && isPreviewOpen.value) {
    closeResumePreview();
  }
};

onMounted(() => {
  window.addEventListener("keydown", handleKeyDown);

  const observer = new IntersectionObserver(
    ([entry]) => {
      if (entry.isIntersecting) {
        isVisible.value = true;
      }
    },
    { threshold: 0.2 },
  );

  const el = document.querySelector("#home");
  if (el) observer.observe(el);
});

onBeforeUnmount(() => {
  window.removeEventListener("keydown", handleKeyDown);
  document.body.style.overflow = "";
});
</script>

<template>
  <section
    id="home"
    class="relative overflow-hidden bg-slate-100/70 dark:bg-none dark:bg-slate-950 transition-colors duration-300 min-h-[calc(100vh-80px)] flex items-center"
  >
    <!-- Ambient Background Glows for Light & Dark Mode -->
    <div
      class="absolute -top-32 right-1/4 w-96 h-96 bg-emerald-400/20 dark:bg-emerald-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>
    <div
      class="absolute top-1/2 -left-20 w-80 h-80 bg-amber-400/20 dark:bg-amber-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>

    <div
      class="relative z-10 max-w-6xl mx-auto px-5 sm:px-8 lg:px-10 py-12 lg:py-16 grid lg:grid-cols-12 gap-12 lg:gap-8 items-center"
    >
      <!-- CONTENT -->
      <div
        :class="[
          'lg:col-span-7 text-center lg:text-left transition-all duration-1000',
          isVisible ? 'opacity-100 translate-y-0' : 'opacity-0 translate-y-8',
        ]"
      >
        <!-- Status Pill Badge -->
        <div
          class="inline-flex items-center gap-2 px-3.5 py-1.5 rounded-full bg-emerald-100/80 dark:bg-emerald-950/60 border border-emerald-300/80 dark:border-emerald-800/60 shadow-xs mb-6"
        >
          <span class="relative flex h-2 w-2">
            <span class="animate-ping absolute inline-flex h-full w-full rounded-full bg-emerald-500 opacity-75"></span>
            <span class="relative inline-flex rounded-full h-2 w-2 bg-emerald-600"></span>
          </span>
          <span class="text-xs font-bold text-emerald-800 dark:text-emerald-300">
            Available for Projects & Remote Opportunities
          </span>
        </div>

        <!-- Heading -->
        <h1
          class="text-4xl sm:text-5xl lg:text-6xl font-extrabold leading-[1.15] tracking-tight text-slate-900 dark:text-white"
        >
          Hi, I'm Gana Purba.
          <span
            class="block mt-2 text-emerald-600 dark:text-emerald-400 font-extrabold"
          >
            Full-Stack Web Developer
          </span>
        </h1>

        <!-- Description -->
        <p
          class="mt-6 text-base sm:text-lg text-slate-700 dark:text-slate-300 max-w-2xl mx-auto lg:mx-0 leading-relaxed font-medium"
        >
          I design and engineer high-performance web applications that deliver real business impact. From robust backend architectures to modern, intuitive user interfaces.
        </p>

        <!-- Highlights -->
        <div class="mt-8 grid grid-cols-3 gap-3 sm:gap-4 max-w-lg mx-auto lg:mx-0">
          <div class="p-3.5 sm:p-4 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md hover:shadow-xl hover:border-emerald-500/40 transition-all">
            <div class="text-xl sm:text-2xl font-black text-emerald-600 dark:text-emerald-400">100%</div>
            <div class="text-xs font-semibold text-slate-600 dark:text-slate-400 mt-1">Clean Code</div>
          </div>
          <div class="p-3.5 sm:p-4 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md hover:shadow-xl hover:border-emerald-500/40 transition-all">
            <div class="text-xl sm:text-2xl font-black text-emerald-600 dark:text-emerald-400">Fast</div>
            <div class="text-xs font-semibold text-slate-600 dark:text-slate-400 mt-1">Responsive UI</div>
          </div>
          <div class="p-3.5 sm:p-4 rounded-2xl bg-white dark:bg-slate-900 border border-slate-200 dark:border-slate-800 shadow-md hover:shadow-xl hover:border-emerald-500/40 transition-all">
            <div class="text-xl sm:text-2xl font-black text-emerald-600 dark:text-emerald-400">End-to-End</div>
            <div class="text-xs font-semibold text-slate-600 dark:text-slate-400 mt-1">Full-Stack Solutions</div>
          </div>
        </div>

        <!-- Action Buttons -->
        <div
          class="mt-8 flex flex-col sm:flex-row justify-center lg:justify-start gap-4"
        >
          <a
            href="#portfolio"
            class="px-7 py-3.5 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-semibold text-sm shadow-md hover:shadow-lg transition-all duration-300 hover:-translate-y-0.5 active:scale-95 flex items-center justify-center gap-2"
          >
            <span>View Selected Work</span>
            <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
            </svg>
          </a>

          <!-- Resume Preview Button -->
          <button
            @click="openResumePreview"
            type="button"
            class="px-7 py-3.5 rounded-xl border border-slate-300 dark:border-slate-700 bg-white dark:bg-slate-900 hover:bg-slate-50 dark:hover:bg-slate-800 text-slate-700 dark:text-slate-200 font-semibold text-sm shadow-xs transition-all duration-300 hover:-translate-y-0.5 active:scale-95 flex items-center justify-center gap-2 cursor-pointer"
          >
            <FontAwesomeIcon
              :icon="['fas', 'download']"
              class="text-emerald-600 dark:text-emerald-400"
            />
            <span>View & Download Resume</span>
          </button>
        </div>
      </div>

      <!-- HERO IMAGE -->
      <div class="lg:col-span-5 flex justify-center order-first lg:order-last">
        <div class="relative group">
          <!-- Soft Glow Overlay -->
          <div
            class="absolute -inset-1 bg-gradient-to-r from-emerald-500/20 to-amber-500/20 rounded-3xl blur-xl opacity-75 group-hover:opacity-100 transition duration-500"
          ></div>

          <!-- Main Image Frame -->
          <div
            class="relative w-64 sm:w-80 lg:w-[380px] aspect-square overflow-hidden rounded-3xl border border-slate-200/80 dark:border-slate-800 bg-slate-100 dark:bg-slate-800 shadow-2xl transition-transform duration-500 group-hover:scale-[1.02]"
          >
            <img
              src="/img/gana1.webp"
              alt="Gana Purba"
              class="w-full h-full object-cover transition duration-700 group-hover:scale-105"
              loading="lazy"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- Resume Preview Modal -->
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
          v-if="isPreviewOpen"
          class="fixed inset-0 z-50 flex items-center justify-center p-3 sm:p-6 bg-slate-950/80 backdrop-blur-md"
          @click.self="closeResumePreview"
        >
          <div
            class="relative w-full max-w-5xl bg-white dark:bg-slate-900 rounded-2xl shadow-2xl border border-slate-200/80 dark:border-slate-800 overflow-hidden flex flex-col max-h-[92vh]"
          >
            <!-- Modal Header -->
            <div class="flex items-center justify-between px-5 sm:px-6 py-4 border-b border-slate-200 dark:border-slate-800 bg-slate-50 dark:bg-slate-950/60">
              <div class="flex items-center gap-3">
                <div class="p-2.5 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 text-emerald-600 dark:text-emerald-400">
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12h6m-6 4h6m2 5H7a2 2 0 01-2-2V5a2 2 0 012-2h5.586a1 1 0 01.707.293l5.414 5.414a1 1 0 01.293.707V19a2 2 0 01-2 2z" />
                  </svg>
                </div>
                <div>
                  <h3 class="text-base font-bold text-slate-900 dark:text-white">
                    Resume / CV Preview
                  </h3>
                  <p class="text-xs text-slate-500 dark:text-slate-400">Gana Purba Kusuma - Full-Stack Web Developer</p>
                </div>
              </div>

              <!-- Header Actions -->
              <div class="flex items-center gap-3">
                <!-- Direct Download Link -->
                <a
                  href="/cv/resume.pdf"
                  download="Resume_Gana_Purba.pdf"
                  class="inline-flex items-center gap-2 px-4 py-2 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-semibold text-xs shadow-sm transition-all active:scale-95"
                >
                  <FontAwesomeIcon :icon="['fas', 'download']" class="w-3.5 h-3.5" />
                  <span>Download PDF</span>
                </a>

                <!-- Close Button -->
                <button
                  @click="closeResumePreview"
                  type="button"
                  class="p-2 rounded-xl text-slate-500 hover:text-slate-800 dark:text-slate-400 dark:hover:text-white hover:bg-slate-200/60 dark:hover:bg-slate-800 transition-colors focus:outline-none"
                  aria-label="Close Preview"
                >
                  <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                  </svg>
                </button>
              </div>
            </div>

            <!-- Modal Body (PDF Viewer) -->
            <div class="flex-1 bg-slate-100 dark:bg-slate-950 p-2 sm:p-4 overflow-hidden relative">
              <iframe
                src="/cv/resume.pdf"
                class="w-full h-[68vh] sm:h-[75vh] rounded-xl border border-slate-200/60 dark:border-slate-800 shadow-inner"
                title="Resume PDF Preview"
              ></iframe>
            </div>
          </div>
        </div>
      </transition>
    </Teleport>
  </section>
</template>
