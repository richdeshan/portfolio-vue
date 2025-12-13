<script setup>
import { ref } from "vue";
import experience from "@/data/experience.json"; // sesuaikan path jika berbeda

const experiences = ref(
  experience.map((exp) => {
    if (exp.endDate.toLowerCase() === "present") {
      exp.duration = calculateDuration(exp.startDate);
    }
    return exp;
  })
);

function calculateDuration(startDateStr) {
  const start = new Date(startDateStr);
  const now = new Date();

  let years = now.getFullYear() - start.getFullYear();
  let months = now.getMonth() - start.getMonth();

  if (months < 0) {
    years--;
    months += 12;
  }

  let durationStr = "";
  if (years > 0) durationStr += `${years} year${years > 1 ? "s" : ""} `;
  if (months > 0) durationStr += `${months} month${months > 1 ? "s" : ""}`;

  return durationStr.trim() || "0 month";
}
</script>

<template>
  <div class="flex flex-col items-center justify-center px-4 py-8">
    <div class="font-bold text-5xl mb-8 text-center">Experience</div>
    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-3 gap-6 w-full max-w-6xl"
    >
      <div
        v-for="(exp, index) in experiences"
        :key="index"
        class="flex flex-col items-center bg-white shadow-md p-6 rounded-lg hover:shadow-xl transition-shadow duration-300"
      >
        <img
          :src="exp.images[0]"
          :alt="exp.company"
          class="w-32 h-32 object-contain mb-4"
        />
        <div class="font-semibold text-lg text-center">{{ exp.company }}</div>
        <div class="text-gray-500 text-center">{{ exp.description }}</div>
        <div class="text-gray-400 text-sm text-center">
          {{ exp.startDate }} - {{ exp.endDate }} ({{ exp.duration }})
        </div>
      </div>
    </div>
  </div>
</template>
