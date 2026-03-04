<script setup></script>

<template>
  <section id="work" class="py-24 bg-white">
    <div class="max-w-5xl mx-auto px-6">
      <!-- Title -->
      <div class="text-center">
        <h2 class="text-4xl font-bold text-slate-900">Work Experience</h2>
        <div class="w-20 h-1 bg-indigo-600 mx-auto mt-6 rounded-full"></div>
        <p class="text-slate-500 mt-6 leading-relaxed">
          Real-world experience building systems that support business
          operations and growth.
        </p>
      </div>

      <!-- Timeline -->
      <div class="relative mt-16">
        <!-- Vertical Line -->
        <div class="absolute left-4 top-0 bottom-0 w-px bg-slate-200"></div>

        <!-- Item -->
        <div class="relative pl-12 mb-12">
          <!-- Dot -->
          <div
            class="absolute left-[9px] top-2 h-4 w-4 rounded-full bg-indigo-600 ring-4 ring-indigo-100"
          ></div>

          <!-- Card -->
          <div
            class="bg-white p-6 rounded-xl border border-slate-200 shadow-sm hover:shadow-xl transition duration-300"
          >
            <!-- Date + Badge -->
            <div class="flex items-center gap-3">
              <p class="text-sm text-slate-400 font-medium">
                May 2024 – Present
              </p>

              <span
                class="text-xs font-semibold bg-indigo-100 text-indigo-700 px-2 py-1 rounded-full"
              >
                Current
              </span>
            </div>

            <h3 class="text-xl font-semibold text-slate-900 mt-2">
              Fullstack Web Developer - Yogya Executive School
            </h3>

            <p class="text-slate-600 mt-3 leading-relaxed">
              Led the development of scalable web applications used by internal
              teams and clients, improving system efficiency and reducing manual
              processes. Delivered clean, maintainable code while ensuring
              performance and long-term stability.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
