<script setup></script>

<template>
  <section id="about" class="relative py-24 bg-slate-100 overflow-hidden">
    <!-- Background Accent -->
    <div
      class="absolute -bottom-32 -left-32 w-96 h-96 bg-orange-300 blur-3xl opacity-20"
    ></div>

    <div class="relative z-10 max-w-6xl mx-auto px-6">
      <!-- Header -->
      <div class="mb-16">
        <div class="flex items-center gap-3 mb-4">
          <div class="w-12 h-[2px] bg-indigo-600"></div>
          <p class="text-md uppercase tracking-widest text-slate-500">
            About Me
          </p>
        </div>

        <!-- <h2 class="text-3xl md:text-4xl font-bold text-slate-900">
          Passionate About Building Reliable Systems
        </h2> -->
        <h2 class="text-3xl md:text-4xl font-bold text-slate-900">
          Helping Startups Build
          <span class="text-indigo-600">Reliable & Scalable</span> Web Solutions
        </h2>
      </div>

      <div class="grid md:grid-cols-2 gap-20 items-start">
        <!-- Left -->
        <div>
          <p class="text-slate-600 leading-relaxed mb-6 text-justify">
            I'm a fullstack developer who enjoys turning ideas into functional
            and user-friendly web applications. I work closely with clients to
            understand their goals and deliver solutions that are practical,
            efficient, and aligned with their business needs.
          </p>

          <p class="text-slate-600 leading-relaxed text-justify">
            From landing pages to full web platforms, I focus on building fast,
            scalable, and maintainable systems — while keeping communication
            clear and the development process simple.
          </p>
          <div class="flex gap-10 mt-8">
            <div>
              <p class="text-2xl font-bold text-slate-900">2+</p>
              <p class="text-sm text-slate-500">Years Experience</p>
            </div>

            <div>
              <p class="text-2xl font-bold text-slate-900">10+</p>
              <p class="text-sm text-slate-500">Projects Completed</p>
            </div>
          </div>
        </div>

        <!-- Right Card -->
        <div
          class="relative bg-white p-8 rounded-2xl shadow-xl border border-slate-200 space-y-6 hover:-translate-y-2 transition duration-500"
        >
          <div>
            <h3 class="font-semibold text-slate-900 mb-1">Frontend</h3>
            <div class="flex flex-wrap gap-2 mt-2">
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >Vue js</span
              >
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >Tailwind</span
              >
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >React js</span
              >
            </div>
          </div>

          <div>
            <h3 class="font-semibold text-slate-900 mb-1">Backend</h3>
            <div class="flex flex-wrap gap-2 mt-2">
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >Codeigniter</span
              >
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >Laravel</span
              >
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full"
                >REST API</span
              >
            </div>
          </div>

          <div>
            <h3 class="font-semibold text-slate-900 mb-1">Database</h3>
            <div class="flex flex-wrap gap-2 mt-2">
              <span class="px-3 py-1 text-xs bg-slate-100 rounded-full">
                MySQL
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
