<script setup>
import { ref } from "vue";
import Button from "../ui/button/Button.vue";

const open = ref(false);

const downloadCV = () => {
  const link = document.createElement("a");
  link.href = "/file/Rich-Deshan-Djuardi-Front-End-Developer-Resume-CV.pdf";
  link.download = "Rich Deshan Djuardi - Resume.pdf"; 
  document.body.appendChild(link);
  link.click();
  document.body.removeChild(link);
};
</script>

<template>
  <header class="w-full py-4 px-6">
    <div class="flex items-center justify-between">
      <div class="text-gray-500 font-semibold text-xl">RICH DESHAN DJUARDI</div>

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
        <Button class="bg-orange-500 hover:bg-orange-300 text-white px-4 py-2"  @click="downloadCV">
          Download CV
        </Button>
      </div>

      <button class="md:hidden flex flex-col gap-1" @click="open = !open">
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
        <span class="w-6 h-[3px] bg-gray-700 rounded"></span>
      </button>
    </div>

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
          @click="downloadCV"
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
