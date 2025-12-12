<script setup>
import { ref } from "vue";
import Button from "../ui/button/Button.vue";

const open = ref(false);
</script>

<template>
  <header class="w-full py-4 px-6">
    <div class="flex items-center justify-between">
      <!-- LOGO -->
      <div class="text-gray-500 font-semibold text-xl">RICH DESHAN DJUARDI</div>

      <!-- DESKTOP MENU -->
      <div class="hidden md:flex items-center gap-6">
        <div class="font-light cursor-pointer hover:text-orange-500">Home</div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          About Me
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Services
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Projects
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Contacts
        </div>
        <Button class="bg-orange-500 hover:bg-orange-300 text-white px-4 py-2">
          Download CV
        </Button>
      </div>

      <!-- MOBILE HAMBURGER -->
      <button class="md:hidden flex flex-col gap-1" @click="open = !open">
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
      </button>
    </div>

    <!-- MOBILE DROPDOWN MENU -->
    <transition name="fade">
      <div
        v-if="open"
        class="flex flex-col gap-4 mt-4 md:hidden bg-white p-4 rounded-lg shadow-md"
      >
        <div class="font-light cursor-pointer hover:text-orange-500">Home</div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          About Me
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Services
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Projects
        </div>
        <div class="font-light cursor-pointer hover:text-orange-500">
          Contacts
        </div>

        <Button
          class="bg-orange-500 hover:bg-orange-300 text-white w-full py-2"
        >
          Download CV
        </Button>
      </div>
    </transition>
  </header>
</template>

<style>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
