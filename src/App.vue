<script setup>
import AboutMe from "./components/body/AboutMe.vue";
import Introduction from "./components/body/Introduction.vue";
import Header from "./components/header/Header.vue";

// logic nanti di sini
</script>

<template>
  <div class="px-[128px]">
    <header class="w-full border-gray-200 py-2">
      <h1><Header></Header></h1>
    </header>

    <!-- BODY -->
    <main class="mx-auto py-12">
      <Introduction />
      <AboutMe />
    </main>

    <!-- FOOTER -->
    <footer class="w-full border-t border-gray-200">
      <div class="mx-auto max-w-6xl px-6 py-6 text-sm text-gray-500">
        © 2025 Your Name. All rights reserved.
      </div>
    </footer>
  </div>
  <!-- HEADER -->
</template>
