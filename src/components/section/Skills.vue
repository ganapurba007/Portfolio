<script setup>
import BootstrapIcon from "../Icon/BootstrapIcon.vue";
import CodeigniterIcon from "../Icon/CodeigniterIcon.vue";
import LaravelIcon from "../Icon/LaravelIcon.vue";
import ReactIcon from "../Icon/ReactIcon.vue";
import TailwindIcon from "../Icon/TailwindIcon.vue";
import VueIcon from "../Icon/VueIcon.vue";
import MysqlIcon from "../Icon/MysqlIcon.vue";
import GitIcon from "../Icon/GitIcon.vue";
import GithubIcon from "../Icon/GithubIcon.vue";
import PostmanIcon from "../Icon/PostmanIcon.vue";
import VscodeIcon from "../Icon/VscodeIcon.vue";
import BitbucketIcon from "../Icon/BitbucketIcon.vue";
</script>

<template>
  <section
    id="skills"
    class="relative py-20 lg:py-28 bg-slate-50/90 dark:bg-slate-950 transition-colors duration-300 overflow-hidden"
  >
    <!-- Background Glow -->
    <div
      class="absolute top-1/3 right-0 w-96 h-96 bg-amber-400/10 dark:bg-amber-500/10 blur-3xl rounded-full pointer-events-none"
    ></div>
    <div class="relative z-10 max-w-6xl mx-auto px-5 sm:px-8">
      <!-- Header -->
      <div class="mb-14 text-center max-w-2xl mx-auto">
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4">
          TECHNICAL SKILLS
        </span>

        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
          Core Technologies & Tools
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400">
          The primary stack and tooling I leverage daily to engineer modern, reliable, and scalable web solutions.
        </p>
      </div>

      <!-- SKILLS GRID CARDS -->
      <div class="grid md:grid-cols-2 gap-6 max-w-5xl mx-auto">
        <!-- FRONTEND -->
        <div class="bg-white dark:bg-slate-900 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs p-6 hover:shadow-md transition-shadow">
          <div class="flex items-center gap-3 mb-5">
            <span class="w-3 h-3 rounded-full bg-emerald-500"></span>
            <h3 class="font-bold text-slate-900 dark:text-white text-lg">Frontend Development</h3>
          </div>

          <div class="grid grid-cols-3 gap-3">
            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <VueIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#4FC08D] transition-colors mb-1.5" />
              <span>Vue.js</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <TailwindIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#06B6D4] transition-colors mb-1.5" />
              <span>Tailwind CSS</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <BootstrapIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#7952B3] transition-colors mb-1.5" />
              <span>Bootstrap</span>
            </div>
          </div>
        </div>

        <!-- BACKEND -->
        <div class="bg-white dark:bg-slate-900 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs p-6 hover:shadow-md transition-shadow">
          <div class="flex items-center gap-3 mb-5">
            <span class="w-3 h-3 rounded-full bg-teal-500"></span>
            <h3 class="font-bold text-slate-900 dark:text-white text-lg">Backend Development</h3>
          </div>

          <div class="grid grid-cols-3 gap-3">
            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <LaravelIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#FF2D20] transition-colors mb-1.5" />
              <span>Laravel</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <CodeigniterIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#EF4223] transition-colors mb-1.5" />
              <span>CodeIgniter</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <GitIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#F05032] transition-colors mb-1.5" />
              <span>RESTful API</span>
            </div>
          </div>
        </div>

        <!-- DATABASE -->
        <div class="bg-white dark:bg-slate-900 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs p-6 hover:shadow-md transition-shadow">
          <div class="flex items-center gap-3 mb-5">
            <span class="w-3 h-3 rounded-full bg-amber-500"></span>
            <h3 class="font-bold text-slate-900 dark:text-white text-lg">Database & Data Layer</h3>
          </div>

          <div class="grid grid-cols-3 gap-3">
            <div class="group flex flex-col items-center justify-center p-3.5 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-xs font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <MysqlIcon class="text-3xl text-slate-700 dark:text-slate-300 group-hover:text-[#4479A1] transition-colors mb-1.5" />
              <span>MySQL</span>
            </div>
          </div>
        </div>

        <!-- TOOLS & WORKFLOW -->
        <div class="bg-white dark:bg-slate-900 rounded-2xl border border-slate-200/80 dark:border-slate-800 shadow-xs p-6 hover:shadow-md transition-shadow">
          <div class="flex items-center gap-3 mb-5">
            <span class="w-3 h-3 rounded-full bg-emerald-500"></span>
            <h3 class="font-bold text-slate-900 dark:text-white text-lg">Developer Tools</h3>
          </div>

          <div class="grid grid-cols-4 gap-2.5">
            <div class="group flex flex-col items-center justify-center p-3 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-[11px] font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <GithubIcon class="text-2xl text-slate-700 dark:text-slate-300 group-hover:text-emerald-500 transition-colors mb-1" />
              <span>GitHub</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-[11px] font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <BitbucketIcon class="text-2xl text-slate-700 dark:text-slate-300 group-hover:text-[#0052CC] transition-colors mb-1" />
              <span>Bitbucket</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-[11px] font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <PostmanIcon class="text-2xl text-slate-700 dark:text-slate-300 group-hover:text-[#FF6C37] transition-colors mb-1" />
              <span>Postman</span>
            </div>

            <div class="group flex flex-col items-center justify-center p-3 rounded-xl bg-slate-50 dark:bg-slate-800/60 border border-slate-200/60 dark:border-slate-700/60 text-[11px] font-medium text-slate-700 dark:text-slate-300 hover:border-emerald-500/50 hover:bg-emerald-50/30 dark:hover:bg-emerald-950/20 hover:-translate-y-0.5 transition-all">
              <VscodeIcon class="text-2xl text-slate-700 dark:text-slate-300 group-hover:text-[#007ACC] transition-colors mb-1" />
              <span>VS Code</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
