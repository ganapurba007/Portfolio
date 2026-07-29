<script setup>
import EmailIcon from "../Icon/EmailIcon.vue";
import GithubIcon from "../Icon/GithubIcon.vue";
import LinkedinIcon from "../Icon/LinkedinIcon.vue";
import WhatsappIcon from "../Icon/WhatsappIcon.vue";
</script>

<template>
  <section id="contact" class="py-20 lg:py-28 bg-slate-50/50 dark:bg-slate-950 transition-colors duration-300">
    <div class="max-w-5xl mx-auto px-5 sm:px-8 text-center">
      <!-- Header -->
      <div class="text-center max-w-2xl mx-auto mb-14">
        <span class="inline-block text-xs uppercase tracking-widest font-semibold text-emerald-600 dark:text-emerald-400 bg-emerald-50 dark:bg-emerald-950/60 px-3.5 py-1 rounded-full border border-emerald-200/50 dark:border-emerald-800/50 mb-4">
          CONTACT ME
        </span>

        <h2 class="text-3xl sm:text-4xl font-extrabold text-slate-900 dark:text-white">
          Let's Connect & Collaborate
        </h2>

        <p class="mt-4 text-base text-slate-600 dark:text-slate-400">
          Open for freelance projects, remote full-time positions, web development consultations, and tech discussions.
        </p>
      </div>

      <!-- Contact Grid -->
      <div class="grid sm:grid-cols-2 gap-4 max-w-4xl mx-auto text-left">
        <!-- WhatsApp -->
        <a
          href="https://wa.me/6285786257585"
          target="_blank"
          rel="noopener noreferrer"
          class="group p-5 sm:p-6 bg-white dark:bg-slate-900 border border-slate-200/80 dark:border-slate-800 rounded-2xl shadow-xs hover:shadow-md hover:border-emerald-500/50 hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <div class="p-3 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 group-hover:scale-110 transition-transform">
            <WhatsappIcon class="text-2xl text-[#25D366]" />
          </div>
          <div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400">WhatsApp Direct</div>
            <div class="text-sm sm:text-base font-bold text-slate-900 dark:text-white group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors">
              +62 857-8625-7585
            </div>
          </div>
        </a>

        <!-- Email -->
        <a
          href="mailto:ganapurbakusuma86@gmail.com"
          class="group p-5 sm:p-6 bg-white dark:bg-slate-900 border border-slate-200/80 dark:border-slate-800 rounded-2xl shadow-xs hover:shadow-md hover:border-emerald-500/50 hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <div class="p-3 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 group-hover:scale-110 transition-transform">
            <EmailIcon class="text-2xl text-[#EA4335]" />
          </div>
          <div class="overflow-hidden">
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400">Primary Email</div>
            <div class="text-sm sm:text-base font-bold text-slate-900 dark:text-white truncate group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors">
              ganapurbakusuma86@gmail.com
            </div>
          </div>
        </a>

        <!-- LinkedIn -->
        <a
          href="https://www.linkedin.com/in/ganapurba/"
          target="_blank"
          rel="noopener noreferrer"
          class="group p-5 sm:p-6 bg-white dark:bg-slate-900 border border-slate-200/80 dark:border-slate-800 rounded-2xl shadow-xs hover:shadow-md hover:border-emerald-500/50 hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <div class="p-3 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 group-hover:scale-110 transition-transform">
            <LinkedinIcon class="text-2xl text-[#0A66C2]" />
          </div>
          <div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400">LinkedIn Profile</div>
            <div class="text-sm sm:text-base font-bold text-slate-900 dark:text-white group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors">
              linkedin.com/in/ganapurba
            </div>
          </div>
        </a>

        <!-- GitHub -->
        <a
          href="https://github.com/ganapurba007"
          target="_blank"
          rel="noopener noreferrer"
          class="group p-5 sm:p-6 bg-white dark:bg-slate-900 border border-slate-200/80 dark:border-slate-800 rounded-2xl shadow-xs hover:shadow-md hover:border-emerald-500/50 hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <div class="p-3 rounded-xl bg-emerald-50 dark:bg-emerald-950/60 border border-emerald-200/50 dark:border-emerald-800/50 group-hover:scale-110 transition-transform">
            <GithubIcon class="text-2xl text-slate-800 dark:text-slate-200" />
          </div>
          <div>
            <div class="text-xs font-medium text-slate-500 dark:text-slate-400">GitHub Repository</div>
            <div class="text-sm sm:text-base font-bold text-slate-900 dark:text-white group-hover:text-emerald-600 dark:group-hover:text-emerald-400 transition-colors">
              github.com/ganapurba007
            </div>
          </div>
        </a>
      </div>
    </div>
  </section>
</template>
