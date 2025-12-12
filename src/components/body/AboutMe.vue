<script setup lang="ts">
import { Image } from "lucide-vue-next";
</script>

<template>
  <div class="w-full p-4 sm:p-6 lg:p-10">
    <div class="grid grid-cols-1 md:grid-cols-2 gap-10 items-center">
      <div class="hidden sm:flex sm:justify-center md:justify-start">
        <img
          src="/images/selfie.png"
          alt="foto saya"
          class="w-56 sm:w-72 md:w-[320px] lg:w-[380px] xl:w-[450px] rounded-xl object-cover shadow-[0_15px_35px_-8px_rgba(251,146,60,0.45)]"
        />
      </div>
      <div class="flex flex-col gap-4">
        <div class="font-bold text-4xl sm:text-5xl">About Me</div>
        <div class="font-light text-lg leading-relaxed">
          I'm a frontend developer with experience in building responsive and
          optimized sites.
        </div>
        <div
          class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-3 lg:grid-cols-4 gap-4 mt-4"
        >
          <img src="/images/vuejs.png" alt="Vue Logo" class="mx-auto" />
          <img
            src="/images/Nextjs-logo.svg.png"
            alt="NextJS Logo"
            class="mx-auto"
          />
          <img src="/images/react.png" alt="React Logo" class="mx-auto" />
          <img src="/images/tailwind.png" alt="Tailwind Logo" class="mx-auto" />
          <img
            src="/images/typescript.png"
            alt="Typescript Logo"
            class="mx-auto"
          />
          <img
            src="/images/restapi-logo.png"
            alt="Rest API Logo"
            class="mx-auto"
          />
          <img src="/images/html.png" alt="HTML Logo" class="mx-auto" />
          <img src="/images/css.png" alt="CSS Logo" class="mx-auto" />
          <img src="/images/js.png" alt="Javascript Logo" class="mx-auto" />
        </div>
      </div>
    </div>
  </div>
</template>
