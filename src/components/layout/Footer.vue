<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="bg-white dark:bg-slate-950 border-t border-slate-200/80 dark:border-slate-800/80 py-8 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-5 sm:px-8 flex flex-col sm:flex-row items-center justify-between gap-4 text-center sm:text-left">
      <div class="flex items-center gap-2">
        <span class="text-base font-bold tracking-tight text-slate-900 dark:text-white">
          Gana Purba<span class="text-emerald-500">.</span>
        </span>
        <span class="text-xs text-slate-400">| Full-Stack Web Developer</span>
      </div>

      <p class="text-xs font-medium text-slate-500 dark:text-slate-400">
        © {{ currentYear }} Gana Purba Kusuma. Engineered for performance & precision.
      </p>
    </div>
  </footer>
</template>
