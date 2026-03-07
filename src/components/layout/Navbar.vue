<script setup>
import { ref, onMounted, onBeforeUnmount, nextTick } from "vue";
import DarkMode from "../Icon/DarkMode.vue";

const activeSection = ref("home");
const isScrolled = ref(false);
const isOpen = ref(false);
const isScrolling = ref(false);

const sections = ref([]);

/* =========================
   EASING FUNCTION
========================= */
const easeInOutCubic = (t) => {
  return t < 0.5 ? 4 * t * t * t : 1 - Math.pow(-2 * t + 2, 3) / 2;
};

/* =========================
   CUSTOM SMOOTH SCROLL
========================= */
const smoothScrollTo = (targetY, duration = 1200) => {
  const startY = window.scrollY;
  const distance = targetY - startY;
  let startTime = null;

  isScrolling.value = true;

  const animation = (currentTime) => {
    if (!startTime) startTime = currentTime;

    const timeElapsed = currentTime - startTime;
    const progress = Math.min(timeElapsed / duration, 1);
    const easedProgress = easeInOutCubic(progress);

    window.scrollTo(0, startY + distance * easedProgress);

    if (timeElapsed < duration) {
      requestAnimationFrame(animation);
    } else {
      isScrolling.value = false;
    }
  };

  requestAnimationFrame(animation);
};

/* =========================
   SCROLL TO SECTION
========================= */
const scrollToSection = (id) => {
  const section = document.getElementById(id);
  if (!section) return;

  const navbarHeight = 100;

  isOpen.value = false;

  // langsung set active
  activeSection.value = id;

  setTimeout(() => {
    const targetY = section.offsetTop - navbarHeight;
    smoothScrollTo(targetY, 1200);
  }, 150);
};

/* =========================
   DETECT ACTIVE SECTION
========================= */
const detectActiveSection = () => {
  const scrollPosition = window.scrollY + 150; // offset navbar

  sections.value.forEach((section) => {
    const offsetTop = section.offsetTop;
    const height = section.offsetHeight;

    if (scrollPosition >= offsetTop && scrollPosition < offsetTop + height) {
      activeSection.value = section.id;
    }
  });
};

/* =========================
   NAVBAR STYLE ON SCROLL
========================= */
const handleScroll = () => {
  isScrolled.value = window.scrollY > 20;

  // jangan update saat animasi smooth scroll
  if (!isScrolling.value) {
    detectActiveSection();
  }
};

/* =========================
   LIFECYCLE
========================= */
onMounted(async () => {
  await nextTick();

  sections.value = Array.from(document.querySelectorAll("section[id]"));

  window.addEventListener("scroll", handleScroll);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <nav
    :class="[
      'fixed w-full z-50 transition-all duration-300',
      isScrolled
        ? 'bg-white/80 dark:bg-slate-900/80 backdrop-blur-md shadow-md'
        : 'bg-transparent',
    ]"
  >
    <div class="max-w-6xl mx-auto px-5">
      <div class="flex justify-between items-center h-20">
        <!-- Logo -->
        <div class="flex items-center gap-3">
          <img
            src="/img/icon.webp"
            class="size-16 object-contain"
            alt="icon_gp"
          />

          <h1
            class="text-4xl font-extrabold tracking-tight bg-gradient-to-r from-indigo-600 via-violet-600 to-fuchsia-600 dark:from-indigo-400 dark:via-violet-400 dark:to-fuchsia-400 bg-clip-text text-transparent"
          >
            Gana Purba
          </h1>
        </div>

        <!-- Desktop Menu -->

        <ul class="hidden lg:flex gap-10 font-medium text-sm">
          <li
            v-for="item in [
              'home',
              'about',
              // 'services',
              'skills',
              'portfolio',
              'work',
              'contact',
            ]"
            :key="item"
          >
            <a
              :href="`#${item}`"
              :class="[
                'relative capitalize transition duration-300',
                activeSection === item
                  ? 'text-slate-600 dark:text-slate-200'
                  : 'text-slate-700 dark:text-slate-300 hover:text-indigo-600 dark:hover:text-indigo-400',
              ]"
              @click.prevent="scrollToSection(item)"
            >
              {{ item }}

              <!-- Underline Animation -->
              <span
                :class="[
                  'absolute left-0 -bottom-1 h-[2px] w-full transition-transform duration-300 origin-left',
                  activeSection === item
                    ? 'bg-indigo-600 dark:bg-indigo-400 scale-x-100'
                    : 'bg-indigo-600 dark:bg-indigo-400 scale-x-0 group-hover:scale-x-100',
                ]"
              ></span>
            </a>
          </li>
          <li>
            <DarkMode class="max-lg:hidden" />
          </li>
        </ul>

        <!-- Mobile Button -->
        <div class="flex items-center gap-5">
          <DarkMode class="lg:hidden" />
          <button
            @click="isOpen = !isOpen"
            class="lg:hidden text-2xl text-slate-900 dark:text-indigo-200"
            aria-label="buttonHamburger"
          >
            ☰
          </button>
        </div>
      </div>
    </div>

    <!-- Mobile Menu -->
    <div
      v-if="isOpen"
      class="lg:hidden bg-white dark:bg-slate-900 shadow-lg border-t"
    >
      <ul class="flex flex-col p-6 gap-4 font-medium">
        <li
          v-for="item in [
            'home',
            'about',
            // 'services',
            'skills',
            'portfolio',
            'work',
            'contact',
          ]"
          :key="item"
        >
          <a
            :href="`#${item}`"
            @click.prevent="scrollToSection(item)"
            :class="[
              'capitalize transition duration-300',
              activeSection === item
                ? 'text-indigo-600 dark:text-indigo-400 font-semibold'
                : 'text-slate-700 dark:text-slate-300 hover:text-indigo-600 dark:hover:text-indigo-400',
            ]"
          >
            {{ item }}
          </a>
        </li>
      </ul>
    </div>
  </nav>
</template>
