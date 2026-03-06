<script setup>
import About from "@/components/section/About.vue";
import Hero from "@/components/section/Hero.vue";
import Portfolio from "@/components/section/Portfolio.vue";
import Work from "@/components/section/Work.vue";
import Services from "@/components/section/Services.vue";
import Cta from "@/components/section/Cta.vue";
import Contact from "@/components/section/Contact.vue";
import Skills from "@/components/section/Skills.vue";
</script>

<template>
  <main>
    <Hero />
    <About />
    <Skills />
    <!-- <Services /> -->
    <Portfolio />
    <Work />
    <Cta />
    <Contact />
  </main>
</template>
