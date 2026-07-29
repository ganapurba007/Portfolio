<script setup>
import { ref, onMounted, onBeforeUnmount } from "vue";
import DarkMode from "../Icon/DarkMode.vue";

const activeSection = ref("home");
const isScrolled = ref(false);
const isOpen = ref(false);

const navItems = [
  { id: "home", label: "Home" },
  { id: "about", label: "About" },
  { id: "skills", label: "Skills" },
  { id: "portfolio", label: "Portfolio" },
  { id: "work", label: "Experience" },
  { id: "contact", label: "Contact" }
];

/* Smooth Scroll to Target Section */
const scrollToSection = (id) => {
  const section = document.getElementById(id);
  if (!section) return;

  isOpen.value = false;
  activeSection.value = id;

  const navbarHeight = 70;
  const targetY = section.getBoundingClientRect().top + window.scrollY - navbarHeight;

  window.scrollTo({
    top: targetY,
    behavior: "smooth"
  });
};

/* Detect Active Section smoothly on Scroll */
const updateActiveSection = () => {
  isScrolled.value = window.scrollY > 20;

  const scrollPosition = window.scrollY;
  const windowHeight = window.innerHeight;
  const documentHeight = document.documentElement.scrollHeight;

  // 1. If reached bottom of page, activate last section ("contact")
  if (scrollPosition + windowHeight >= documentHeight - 50) {
    activeSection.value = "contact";
    return;
  }

  // 2. Determine active section based on top offset threshold
  const offsetThreshold = 180;
  const navItemIds = navItems.map((item) => item.id);
  let bestMatch = "home";

  for (const id of navItemIds) {
    const el = document.getElementById(id);
    if (el) {
      const rect = el.getBoundingClientRect();
      if (rect.top <= offsetThreshold) {
        bestMatch = id;
      }
    }
  }

  activeSection.value = bestMatch;
};

onMounted(() => {
  window.addEventListener("scroll", updateActiveSection, { passive: true });
  window.addEventListener("resize", updateActiveSection, { passive: true });
  updateActiveSection();
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", updateActiveSection);
  window.removeEventListener("resize", updateActiveSection);
});
</script>

<template>
  <header
    :class="[
      'fixed top-0 left-0 w-full z-50 transition-all duration-300',
      isScrolled
        ? 'bg-white/95 dark:bg-slate-950/95 backdrop-blur-xl border-b border-slate-200/90 dark:border-slate-800/90 shadow-sm py-3'
        : 'bg-white/80 dark:bg-slate-950/80 backdrop-blur-md border-b border-slate-200/60 dark:border-slate-800/60 py-4'
    ]"
  >
    <div class="max-w-6xl mx-auto px-5 sm:px-8">
      <div class="flex justify-between items-center h-12">
        <!-- Logo Brand -->
        <a
          href="#home"
          @click.prevent="scrollToSection('home')"
          class="flex items-center gap-3 group focus:outline-none"
        >
          <div class="relative w-10 h-10 p-1 rounded-xl bg-white dark:bg-white shadow-xs border border-slate-200/80 dark:border-slate-200 group-hover:scale-105 transition-transform duration-300 flex items-center justify-center">
            <img
              src="/img/icon.webp"
              alt="Gana Purba Logo"
              class="w-full h-full object-contain"
            />
          </div>

          <span class="text-xl font-extrabold tracking-tight text-slate-900 dark:text-white transition-colors">
            Gana Purba
          </span>
        </a>

        <!-- Desktop Navigation: Active Pill updates dynamically on scroll -->
        <nav class="hidden lg:flex items-center gap-1 bg-slate-200/70 dark:bg-slate-900/90 p-1.5 rounded-full border border-slate-300/70 dark:border-slate-800 backdrop-blur-md">
          <a
            v-for="item in navItems"
            :key="item.id"
            :href="`#${item.id}`"
            @click.prevent="scrollToSection(item.id)"
            :class="[
              'relative px-4 py-1.5 text-xs font-bold rounded-full transition-all duration-300 cursor-pointer select-none',
              activeSection === item.id
                ? 'bg-emerald-600 dark:bg-emerald-500 text-white shadow-md font-bold scale-[1.03]'
                : 'text-slate-700 dark:text-slate-200 hover:bg-slate-300/70 dark:hover:bg-slate-800 hover:text-emerald-700 dark:hover:text-emerald-300'
            ]"
          >
            {{ item.label }}
          </a>
        </nav>

        <!-- Right Utilities & CTA -->
        <div class="hidden lg:flex items-center gap-4">
          <DarkMode />

          <a
            href="#contact"
            @click.prevent="scrollToSection('contact')"
            class="inline-flex items-center gap-2 text-xs font-bold px-4 py-2 rounded-full bg-emerald-600 hover:bg-emerald-500 text-white shadow-sm hover:shadow-md transition-all duration-200 active:scale-95"
          >
            <span>Let's Talk</span>
            <svg class="w-3.5 h-3.5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
            </svg>
          </a>
        </div>

        <!-- Mobile Action Buttons -->
        <div class="flex lg:hidden items-center gap-3">
          <DarkMode />

          <button
            @click="isOpen = !isOpen"
            type="button"
            class="p-2 rounded-xl text-slate-800 dark:text-slate-200 hover:bg-slate-100 dark:hover:bg-slate-800 transition-colors focus:outline-none border border-slate-200 dark:border-slate-800"
            :aria-expanded="isOpen"
            aria-label="Toggle navigation menu"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path
                v-if="!isOpen"
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M4 6h16M4 12h16M4 18h16"
              />
              <path
                v-else
                stroke-linecap="round"
                stroke-linejoin="round"
                stroke-width="2"
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Dropdown Menu -->
    <transition
      enter-active-class="transition duration-200 ease-out"
      enter-from-class="opacity-0 -translate-y-2 scale-95"
      enter-to-class="opacity-100 translate-y-0 scale-100"
      leave-active-class="transition duration-150 ease-in"
      leave-from-class="opacity-100 translate-y-0 scale-100"
      leave-to-class="opacity-0 -translate-y-2 scale-95"
    >
      <div
        v-if="isOpen"
        class="lg:hidden absolute top-full left-0 w-full bg-white/95 dark:bg-slate-950/95 backdrop-blur-xl border-b border-slate-200 dark:border-slate-800 shadow-xl px-5 py-6"
      >
        <div class="flex flex-col gap-2">
          <a
            v-for="item in navItems"
            :key="item.id"
            :href="`#${item.id}`"
            @click.prevent="scrollToSection(item.id)"
            :class="[
              'flex items-center justify-between px-4 py-3 rounded-xl text-sm font-semibold transition-all',
              activeSection === item.id
                ? 'bg-emerald-600 text-white font-bold shadow-sm'
                : 'text-slate-800 dark:text-slate-200 hover:bg-slate-100 dark:hover:bg-slate-900 hover:text-emerald-600 dark:hover:text-emerald-400'
            ]"
          >
            <span>{{ item.label }}</span>
            <span
              v-if="activeSection === item.id"
              class="w-2 h-2 rounded-full bg-white"
            ></span>
          </a>

          <div class="pt-4 mt-2 border-t border-slate-200 dark:border-slate-800">
            <a
              href="#contact"
              @click.prevent="scrollToSection('contact')"
              class="flex items-center justify-center gap-2 w-full py-3 rounded-xl bg-emerald-600 hover:bg-emerald-500 text-white font-bold text-sm shadow-md transition-all active:scale-95"
            >
              <span>Get in Touch</span>
              <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3" />
              </svg>
            </a>
          </div>
        </div>
      </div>
    </transition>
  </header>
</template>
