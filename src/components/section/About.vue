<script setup></script>

<template>
  <section id="about" class="relative py-24 bg-slate-200 overflow-hidden">
    <!-- Background Accent -->
    <div
      class="absolute -bottom-32 -left-32 w-96 h-96 bg-orange-300 blur-3xl opacity-20"
    ></div>

    <div class="relative z-10 max-w-6xl mx-auto px-6">
      <!-- HEADER -->
      <div class="mb-14">
        <div class="flex justify-center items-center gap-3 mb-4">
          <div class="w-12 h-[2px] bg-indigo-600"></div>
          <p class="text-md uppercase tracking-widest text-slate-500">
            About Me
          </p>
          <div class="w-12 h-[2px] bg-indigo-600"></div>
        </div>

        <h2 class="text-3xl md:text-4xl font-bold text-slate-900 leading-tight">
          Helping Startups Build
          <span class="text-indigo-600">Reliable & Scalable</span>
          Web Solutions
        </h2>
      </div>

      <!-- ABOUT TEXT -->
      <div class="max-w-3xl">
        <p class="text-slate-600 leading-relaxed mb-6 text-justify">
          I'm a fullstack developer who enjoys turning ideas into functional and
          user-friendly web applications. I work closely with clients to
          understand their goals and deliver solutions that are practical,
          efficient, and aligned with their business needs.
        </p>

        <p class="text-slate-600 leading-relaxed text-justify">
          From landing pages to full web platforms, I focus on building fast,
          scalable, and maintainable systems — while keeping communication clear
          and the development process simple.
        </p>

        <!-- STATS -->
        <div class="flex gap-12 mt-8">
          <div>
            <p class="text-3xl font-bold text-slate-900">2+</p>
            <p class="text-sm text-slate-500">Years Experience</p>
          </div>

          <div>
            <p class="text-3xl font-bold text-slate-900">10+</p>
            <p class="text-sm text-slate-500">Projects Completed</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
