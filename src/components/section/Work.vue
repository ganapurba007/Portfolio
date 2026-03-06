<script setup></script>

<template>
  <section id="work" class="py-10 bg-white">
    <div class="max-w-5xl mx-auto px-6">
      <!-- Title -->
      <div class="text-center">
        <div class="flex justify-center items-center gap-3 mb-3">
          <div class="w-10 h-[2px] bg-indigo-600"></div>
          <p class="text-sm uppercase tracking-widest text-slate-500">
            Experience
          </p>
          <div class="w-10 h-[2px] bg-indigo-600"></div>
        </div>

        <h2 class="text-3xl font-bold text-slate-900">
          Work <span class="text-indigo-600">Experience</span>
        </h2>

        <p class="mt-3 text-slate-600 max-w-lg mx-auto text-sm">
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
