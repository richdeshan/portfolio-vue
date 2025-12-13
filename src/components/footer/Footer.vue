<script setup>
const contacts = [
  {
    label: "Email",
    value: "richdeshan@gmail.com",
    href: "mailto:richdeshan@gmail.com",
  },
  {
    label: "WhatsApp",
    value: "089651138095",
    href: "https://wa.me/6289651138095?text=Hello%20Rich",
  },
  {
    label: "LinkedIn",
    value: "Rich Deshan Djuardi",
    href: "https://www.linkedin.com/in/richdjuardi/",
  },
  {
    label: "GitHub",
    value: "starspen",
    href: "https://github.com/starspen",
  },
];
</script>


<template>
  <div class="w-full py-8 px-4 sm:px-6 md:px-10 lg:px-20 xl:px-32 bg-white/50 backdrop-blur-md border-t border-orange-100/70">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row justify-between gap-6 items-start">
      <!-- Deskripsi -->
      <div class="flex-1 mb-4 md:mb-0">
        <h2 class="text-2xl font-bold text-gray-700 mb-2">Contact Me</h2>
        <p class="text-gray-500 text-sm sm:text-base">
          Feel free to reach out to me via email, WhatsApp, or my social profiles.
        </p>
      </div>

      <!-- Info kontak -->
      <div class="flex-1 flex flex-col gap-3">
        <div
          v-for="contact in contacts"
          :key="contact.label"
          class="flex flex-col sm:flex-row sm:items-center gap-1 sm:gap-2"
        >
          <span class="font-semibold text-gray-600 min-w-[90px]">{{ contact.label }}:</span>
          <a
            :href="contact.href"
            class="text-orange-500 hover:text-orange-400 transition-colors break-words"
            target="_blank"
            rel="noopener noreferrer"
          >
            {{ contact.value }}
          </a>
        </div>
      </div>
    </div>
  </div>
</template>
