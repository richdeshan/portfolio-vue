<script setup>
import AboutMe from "./components/body/AboutMe.vue";
import Introduction from "./components/body/Introduction.vue";
import Projects from "./components/body/Projects.vue";
import Header from "./components/header/Header.vue";
</script>

<template>
  <div
    class="min-h-screen bg-gradient-to-br from-orange-50 via-white to-orange-200 relative overflow-hidden"
  >
    <div
      class="absolute inset-0 opacity-[0.25] pointer-events-none"
      style="
        background-image: url('https://grainy-gradients.vercel.app/noise.svg');
        mix-blend-mode: soft-light;
      "
    ></div>

    <div class="relative z-10 w-full">
      <header
        class="w-full border-b border-orange-100/70 py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 backdrop-blur-md bg-white/40"
      >
        <h1>
          <Header />
        </h1>
      </header>

      <main
        class="mx-auto py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 max-w-6xl"
      >
        <div class="flex flex-col gap-4">
          <Introduction />
          <AboutMe />
          <Projects />
        </div>
      </main>

      <footer
        class="w-full border-t border-orange-100/70 bg-white/50 backdrop-blur-md"
      >
        <div
          class="mx-auto max-w-6xl px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 py-6 text-sm text-gray-600"
        >
          © 2025 Your Name. All rights reserved.
        </div>
      </footer>
    </div>
  </div>
</template>
