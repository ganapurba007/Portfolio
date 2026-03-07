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
    class="relative py-24 overflow-hidden bg-white dark:bg-slate-900"
  >
    <div class="relative z-10 max-w-6xl mx-auto px-6">
      <!-- Header -->
      <div class="mb-10 text-center">
        <div class="flex justify-center items-center gap-3 mb-3">
          <div class="w-10 h-[2px] bg-indigo-600 dark:bg-white"></div>
          <p
            class="text-sm uppercase tracking-widest text-slate-500 dark:text-slate-400"
          >
            Skills
          </p>
          <div class="w-10 h-[2px] bg-indigo-600 dark:bg-white"></div>
        </div>

        <h2 class="text-3xl font-bold text-slate-900 dark:text-slate-100">
          My
          <span class="text-indigo-600 dark:text-indigo-400">Tech Stack</span>
        </h2>

        <p
          class="mt-3 text-slate-600 dark:text-slate-400 max-w-lg mx-auto text-md"
        >
          Technologies and tools I use to build modern, scalable, and reliable
          web applications.
        </p>
      </div>

      <!-- SKILLS CARD -->
      <div
        class="bg-white bg-opacity-50 dark:bg-slate-800 rounded-2xl border border-slate-200 dark:border-slate-700 shadow-sm p-6 space-y-6"
      >
        <!-- FRONTEND -->
        <div>
          <h3
            class="font-semibold text-slate-900 dark:text-slate-100 mb-3 flex items-center gap-2 text-lg"
          >
            <span
              class="w-2 h-2 rounded-full bg-orange-400 dark:bg-orange-300"
            ></span>
            Frontend
          </h3>

          <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <VueIcon
                class="text-2xl text-slate-700 group-hover:text-[#4FC08D] dark:text-slate-400 dark:group-hover:text-[#4FC08D]"
              />
              <span>Vue</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <TailwindIcon
                class="text-2xl text-slate-700 group-hover:text-[#06B6D4] dark:text-slate-400 dark:group-hover:text-[#06B6D4]"
              />
              <span>Tailwind</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <BootstrapIcon
                class="text-2xl text-slate-700 group-hover:text-[#7952B3] dark:text-slate-400 dark:group-hover:text-[#7952B3]"
              />
              <span>Bootstrap</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <ReactIcon
                class="text-2xl text-slate-700 group-hover:text-[#61DAFB] dark:text-slate-400 dark:group-hover:text-[#61DAFB]"
              />
              <span>React</span>
            </div>
          </div>
        </div>

        <!-- BACKEND -->
        <div>
          <h3
            class="font-semibold text-slate-900 mb-3 flex items-center gap-2 text-lg"
          >
            <span class="w-2 h-2 rounded-full bg-indigo-400"></span>
            Backend
          </h3>

          <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <CodeigniterIcon
                class="text-2xl text-slate-700 group-hover:text-[#EF4223] dark:text-slate-400 dark:group-hover:text-[#EF4223]"
              />
              <span>CodeIgniter</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <LaravelIcon
                class="text-2xl text-slate-700 group-hover:text-[#FF2D20] dark:text-slate-400 dark:group-hover:text-[#FF2D20]"
              />
              <span>Laravel</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <GitIcon
                class="text-2xl text-slate-700 group-hover:text-[#F05032] dark:text-slate-400 dark:group-hover:text-[#F05032]"
              />
              <span>Git</span>
            </div>

            <div
              class="flex items-center justify-center text-xs p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              REST API
            </div>
          </div>
        </div>

        <!-- DATABASE -->
        <div>
          <h3
            class="font-semibold text-slate-900 dark:text-slate-100 mb-3 flex items-center gap-2"
          >
            <span
              class="w-2 h-2 rounded-full bg-blue-400 dark:bg-blue-300"
            ></span>
            Database
          </h3>

          <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <MysqlIcon
                class="text-2xl text-slate-700 group-hover:text-[#4479A1] dark:text-slate-400 dark:group-hover:text-[#4479A1]"
              />
              <span>MySQL</span>
            </div>
          </div>
        </div>

        <!-- TOOLS -->
        <div>
          <h3
            class="font-semibold text-slate-900 dark:text-slate-100 mb-3 flex items-center gap-2 text-lg"
          >
            <span
              class="w-2 h-2 rounded-full bg-emerald-400 dark:bg-emerald-300"
            ></span>
            Tools
          </h3>

          <div class="grid grid-cols-2 sm:grid-cols-4 gap-3">
            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <GithubIcon
                class="text-2xl text-slate-700 group-hover:text-[#181717] dark:text-slate-400 dark:group-hover:text-[#181717]"
              />
              <span>GitHub</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <BitbucketIcon
                class="text-2xl text-slate-700 group-hover:text-[#0052CC] dark:text-slate-400 dark:group-hover:text-[#0052CC]"
              />
              <span>Bitbucket</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <PostmanIcon
                class="text-2xl text-slate-700 group-hover:text-[#FF6C37] dark:text-slate-400 dark:group-hover:text-[#FF6C37]"
              />
              <span>Postman</span>
            </div>

            <div
              class="group flex flex-col items-center justify-center gap-1 p-3 rounded-lg bg-slate-50 dark:bg-slate-800 border border-slate-200 dark:border-slate-700 text-xs text-slate-700 dark:text-slate-400 font-medium transition hover:shadow-md hover:-translate-y-1"
            >
              <VscodeIcon
                class="text-2xl text-slate-700 group-hover:text-[#007ACC] dark:text-slate-400 dark:group-hover:text-[#007ACC]"
              />
              VS Code
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
