<script setup>
import { ref } from "vue";
const isDark = ref(false);
const textMode = ref("Light Mode");
function toggleClick() {
  document.documentElement.classList.toggle("dark", isDark.value);
  isDark.value = !isDark.value;
  textMode.value = isDark.value ? "Dark Mode" : "Light Mode";
}
</script>

<template>
  <label class="flex items-center gap-2 cursor-pointer">
    <!-- Icon Light -->
    <span class="text-yellow-500 text-lg">☀️</span>

    <!-- Toggle -->
    <input type="checkbox" class="sr-only peer" @change="toggleClick" />

    <div
      class="relative w-11 h-6 bg-slate-300 rounded-full peer-checked:bg-slate-700 after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:h-5 after:w-5 after:rounded-full after:transition-all peer-checked:after:translate-x-full"
    ></div>

    <!-- Icon Dark -->
    <span class="text-slate-800 dark:text-white text-lg">🌙</span>
  </label>
</template>
