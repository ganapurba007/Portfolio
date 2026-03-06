<script setup>
import EmailIcon from "../Icon/EmailIcon.vue";
import GithubIcon from "../Icon/GithubIcon.vue";
import LinkedinIcon from "../Icon/LinkedinIcon.vue";
import WhatsappIcon from "../Icon/WhatsappIcon.vue";
</script>

<template>
  <section id="contact" class="py-10 bg-slate-200">
    <div class="max-w-5xl mx-auto px-6 text-center">
      <!-- Header -->
      <div class="text-center">
        <div class="flex justify-center items-center gap-3 mb-3">
          <div class="w-10 h-[2px] bg-indigo-600"></div>
          <p class="text-sm uppercase tracking-widest text-slate-500">
            Contact
          </p>
          <div class="w-10 h-[2px] bg-indigo-600"></div>
        </div>

        <h2 class="text-3xl font-bold text-slate-900">
          Let's <span class="text-indigo-600">Connect</span>
        </h2>

        <p class="mt-3 text-slate-600 max-w-lg mx-auto text-sm">
          I'm open to freelance opportunities, collaborations, or professional
          discussions.
        </p>
      </div>

      <!-- Contact Grid -->
      <div class="mt-16 grid md:grid-cols-2 gap-8 text-left">
        <!-- Email -->
        <a
          href="mailto:ganapurbakusuma86@gmail.com"
          class="p-6 bg-white border border-slate-200 rounded-2xl hover:shadow-lg hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <EmailIcon class="text-[#EA4335]" />
          <p class="text-lg font-medium text-slate-900">
            ganapurbakusuma86@gmail.com
          </p>
        </a>

        <!-- LinkedIn -->
        <a
          href="https://www.linkedin.com/in/ganapurba/"
          target="_blank"
          class="p-6 bg-white border border-slate-200 rounded-2xl hover:shadow-lg hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <LinkedinIcon />
          <p class="text-lg font-medium text-slate-900">
            linkedin.com/in/ganapurba
          </p>
        </a>

        <!-- GitHub -->
        <a
          href="https://github.com/ganapurba007"
          target="_blank"
          class="p-6 bg-white border border-slate-200 rounded-2xl hover:shadow-lg hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <GithubIcon class="text-[#181717]" />
          <p class="text-lg font-medium text-slate-900">
            github.com/ganapurba007
          </p>
        </a>

        <!-- WhatsApp -->
        <a
          href="https://wa.me/6285786257585"
          target="_blank"
          class="p-6 bg-white border border-slate-200 rounded-2xl hover:shadow-lg hover:-translate-y-1 transition-all duration-300 flex items-center gap-4"
        >
          <WhatsappIcon class="text-[#25D366]" />
          <p class="text-lg font-medium text-slate-900">+62 857 8625 7585</p>
        </a>
      </div>
    </div>
  </section>
</template>
