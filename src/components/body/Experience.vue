<script setup lang="ts">
import { ref } from "vue";
import experience from "@/data/experience.json";

interface Experience {
  company: string;
  description: string;
  startDate: string; 
  endDate: string;
  images: string[];
  duration?: string;
}
function parseDateSafely(dateStr: string): Date {
  const [year, month] = dateStr.split("-").map(Number);

  if (!year || !month) {
    throw new Error(`Invalid date format: ${dateStr}`);
  }

  return new Date(year, month - 1, 1);
}

function calculateDuration(startDateStr: string): string {
  const start: Date = parseDateSafely(startDateStr);
  const now: Date = new Date();

  let years: number = now.getFullYear() - start.getFullYear();
  let months: number = now.getMonth() - start.getMonth();

  if (months < 0) {
    years--;
    months += 12;
  }

  const yearText = years > 0 ? `${years} year${years > 1 ? "s" : ""}` : "";
  const monthText = months > 0 ? `${months} month${months > 1 ? "s" : ""}` : "";

  return [monthText, yearText].filter(Boolean).join(" ") || "0 month";
}
const experiences = ref<Experience[]>(
  (experience as Experience[]).map((exp) => {
    if (exp.endDate.toLowerCase() === "present") {
      exp.duration = calculateDuration(exp.startDate);
    }
    return exp;
  })
);
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
          {{ exp.startDate }} to {{ exp.endDate }} ({{ exp.duration }})
        </div>
      </div>
    </div>
  </div>
</template>
