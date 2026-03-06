<script setup>
import BootstrapIcon from "../Icon/BootstrapIcon.vue";
import CodeigniterIcon from "../Icon/CodeigniterIcon.vue";
import LaravelIcon from "../Icon/LaravelIcon.vue";
import ReactIcon from "../Icon/ReactIcon.vue";
import TailwindIcon from "../Icon/TailwindIcon.vue";
import VueIcon from "../Icon/VueIcon.vue";
import MysqlIcon from "../Icon/MysqlIcon.vue";
import GitIcon from "../Icon/GitIcon.vue";
</script>

<template>
  <section id="about" class="relative py-24 bg-slate-200 overflow-hidden">
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
          class="relative bg-gradient-to-br from-white to-slate-50 p-8 rounded-2xl shadow-xl border border-slate-200 space-y-10 overflow-hidden"
        >
          <!-- Glow Decoration -->
          <div
            class="absolute -top-16 -right-16 w-48 h-48 bg-orange-300 opacity-20 blur-3xl rounded-full"
          ></div>

          <!-- Frontend -->
          <div>
            <h3
              class="font-semibold text-slate-900 text-lg mb-4 flex items-center gap-2"
            >
              <span class="w-1.5 h-6 bg-orange-400 rounded"></span>
              Frontend
            </h3>

            <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <VueIcon
                  class="text-3xl text-slate-700 group-hover:text-[#4FC08D]"
                />
                <span class="text-xs text-slate-600 font-medium">Vue</span>
              </div>

              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <TailwindIcon
                  class="text-3xl text-slate-700 group-hover:text-[#06B6D4]"
                />
                <span class="text-xs text-slate-600 font-medium">Tailwind</span>
              </div>

              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <BootstrapIcon
                  class="text-3xl text-slate-700 group-hover:text-[#7952B3]"
                />
                <span class="text-xs text-slate-600 font-medium"
                  >Bootstrap</span
                >
              </div>

              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <ReactIcon
                  class="text-3xl text-slate-700 group-hover:text-[#61DAFB]"
                />
                <span class="text-xs text-slate-600 font-medium">React</span>
              </div>
            </div>
          </div>

          <!-- Backend -->
          <div>
            <h3
              class="font-semibold text-slate-900 text-lg mb-4 flex items-center gap-2"
            >
              <span class="w-1.5 h-6 bg-indigo-400 rounded"></span>
              Backend
            </h3>

            <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <CodeigniterIcon
                  class="text-3xl text-slate-700 group-hover:text-[#EF4223]"
                />
                <span class="text-xs text-slate-600 font-medium"
                  >CodeIgniter</span
                >
              </div>

              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <LaravelIcon
                  class="text-3xl text-slate-700 group-hover:text-[#FF2D20]"
                />
                <span class="text-xs text-slate-600 font-medium">Laravel</span>
              </div>

              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <GitIcon
                  class="text-3xl text-slate-700 group-hover:text-[#F05032]"
                />
                <span class="text-xs text-slate-600 font-medium">Git</span>
              </div>

              <div
                class="flex items-center justify-center text-xs bg-slate-100 px-3 py-3 rounded-xl font-medium hover-skills"
              >
                REST API
              </div>
            </div>
          </div>

          <!-- Database -->
          <div>
            <h3
              class="font-semibold text-slate-900 text-lg mb-4 flex items-center gap-2"
            >
              <span class="w-1.5 h-6 bg-blue-400 rounded"></span>
              Database
            </h3>

            <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
              <div
                class="group flex flex-col items-center gap-2 p-4 rounded-xl bg-slate-100 hover-skills"
              >
                <MysqlIcon
                  class="text-3xl text-slate-700 group-hover:text-[#4479A1]"
                />
                <span class="text-xs text-slate-600 font-medium">MySQL</span>
              </div>
            </div>
          </div>

          <!-- Tools -->
          <div>
            <h3
              class="font-semibold text-slate-900 text-lg mb-4 flex items-center gap-2"
            >
              <span class="w-1.5 h-6 bg-emerald-400 rounded"></span>
              Tools
            </h3>

            <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
              <div
                class="flex items-center justify-center text-xs bg-slate-100 px-4 py-3 rounded-xl font-medium hover-skills"
              >
                GitHub
              </div>

              <div
                class="flex items-center justify-center text-xs bg-slate-100 px-4 py-3 rounded-xl font-medium hover-skills"
              >
                Postman
              </div>

              <div
                class="flex items-center justify-center text-xs bg-slate-100 px-4 py-3 rounded-xl font-medium hover-skills"
              >
                VS Code
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
