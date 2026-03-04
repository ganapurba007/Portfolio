<script setup>
const currentYear = new Date().getFullYear();
</script>

<template>
  <footer class="bg-slate-900 border-t border-slate-800">
    <div class="max-w-6xl mx-auto px-6 py-10 text-center">
      <p class="text-sm text-slate-400 tracking-wide">
        © {{ currentYear }}
        <span class="font-semibold text-white"> Gana Purba Kusuma </span>. All
        rights reserved.
      </p>
    </div>
  </footer>
</template>
