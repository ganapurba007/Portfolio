<script setup>
const props = defineProps({
  service: Object,
});
</script>
<template>
  <div
    class="p-8 border border-slate-200 rounded-2xl hover:shadow-xl transition-all duration-300"
  >
    <h3 class="text-xl font-semibold text-slate-900 mb-4">
      {{ props.service.title }}
    </h3>
    <p class="text-slate-600 leading-relaxed">
      {{ props.service.description }}
    </p>
  </div>
</template>
<style setup></style>
