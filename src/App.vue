<script setup>
import AboutMe from "./components/body/AboutMe.vue";
import Introduction from "./components/body/Introduction.vue";
import Projects from "./components/body/Projects.vue";
import Header from "./components/header/Header.vue";
</script>

<template>
  <div class="w-full">
    <!-- HEADER -->
    <header
      class="w-full border-gray-200 py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32"
    >
      <h1>
        <Header />
      </h1>
    </header>

    <!-- BODY -->
    <main
      class="mx-auto py-2 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 max-w-6xl"
    >
      <div class="flex flex-col gap-10">
        <Introduction />
        <AboutMe />
        <Projects />
      </div>
    </main>

    <!-- FOOTER -->
    <footer class="w-full border-t border-gray-200">
      <div
        class="mx-auto max-w-6xl px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 py-6 text-sm text-gray-500"
      >
        © 2025 Your Name. All rights reserved.
      </div>
    </footer>
  </div>
</template>
