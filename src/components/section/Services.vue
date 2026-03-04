<script setup>
import { services } from "../../data/services.json";
import Service from "../layout/Service.vue";
</script>

<template>
  <section id="services" class="relative py-24 bg-white overflow-hidden">
    <div class="max-w-6xl mx-auto px-6">
      <!-- Header -->
      <div class="text-center max-w-2xl mx-auto">
        <h2 class="text-4xl font-bold text-slate-900">Services</h2>

        <div class="w-20 h-1 bg-indigo-600 mx-auto mt-6 rounded-full"></div>

        <p class="text-slate-500 mt-6 leading-relaxed">
          Solutions I offer to help businesses build fast, scalable, and
          reliable web applications.
        </p>
      </div>

      <!-- Grid -->
      <div class="mt-20 grid md:grid-cols-2 gap-10">
        <!-- Service  -->
        <Service
          v-for="service in services"
          :key="service.id"
          :service="service"
        />
      </div>
    </div>
  </section>
</template>

<style scoped></style>
