<script setup>
async function navigateToEventCounter() {
  await navigateTo("/event-countdown");
}
async function navigateToSemesterWeekNum() {
  await navigateTo("/semester-week-num");
}
</script>

<template>
  <div class="flex flex-col space-y-3 h-screen justify-center items-center">
    <button
      v-on:click="navigateToEventCounter()"
      class="border p-2 rounded bg-gray-100 hover:bg-gray-300 hover:shadow-lg"
    >
      Event Countdown
    </button>
    <button
      v-on:click="navigateToSemesterWeekNum()"
      class="border p-2 rounded bg-gray-100 hover:bg-gray-300 hover:shadow-lg"
    >
      Semester Week #
    </button>
  </div>
</template>
