<script setup lang="ts"></script>

<template>
  <div class="w-full p-4">
    <!-- Responsive Grid -->
    <div class="grid grid-cols-1 md:grid-cols-3 gap-10 md:gap-20 items-center">
      <!-- TEXT -->
      <div class="flex flex-col gap-2 col-span-2 order-2 md:order-1">
        <div class="text-lg md:text-xl">Hi I am,</div>

        <div class="font-semibold text-orange-500 text-2xl md:text-3xl">
          Rich Deshan Djuardi,
        </div>

        <div class="font-bold text-4xl md:text-5xl leading-tight">
          Front End Developer
        </div>

        <div class="font-light text-sm md:text-base leading-relaxed">
          I am a front-end web developer with a strong passion for building
          clean, modern, and user-friendly web applications. With hands-on
          experience in Next.js, React, Vue, Tailwind CSS, shadcn/ui, TanStack
          Query, and REST APIs, I focus on delivering responsive interfaces and
          scalable solutions. I’m always eager to learn new technologies and
          continuously refine my craft to create impactful digital experiences.
          Let’s work together to build exceptional products!
        </div>
      </div>

      <!-- PHOTO -->
      <div
        class="relative w-40 h-40 md:w-60 md:h-60 mx-auto order-1 md:order-2"
      >
        <div
          class="absolute inset-0 rounded-full p-1 bg-gradient-to-tr from-pink-500 via-purple-500 to-blue-500 animate-spin-slow"
        >
          <div class="w-full h-full rounded-full bg-white"></div>
        </div>

        <img
          src="/images/selfie2.png"
          class="absolute inset-0 w-full h-full rounded-full object-cover p-[6px]"
        />
      </div>
    </div>
  </div>
</template>

<style>
.animate-spin-slow {
  animation: spin 6s linear infinite;
}

@keyframes spin {
  to {
    transform: rotate(360deg);
  }
}
</style>
