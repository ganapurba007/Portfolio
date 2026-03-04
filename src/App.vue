<script setup>
import Navbar from "@/components/layout/Navbar.vue";
import Footer from "@/components/layout/Footer.vue";
</script>

<template>
  <div class="bg-white text-slate-800 scroll-smooth">
    <Navbar />
    <router-view />
    <Footer />
  </div>
</template>

<style scoped></style>
