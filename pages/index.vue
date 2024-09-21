<script setup>
async function nav(str) {
  await navigateTo(`/${str}`);
}
</script>

<template>
  <div
    class="flex flex-col space-y-3 justify-center items-center h-w-screen h-screen bg-gray-900 text-white"
  >
    <button
      class="border-2 border-gray-500 px-4 py-2 rounded-full text-black bg-gray-200 hover:bg-gray-500 hover:text-white hover:border-white"
      @click="nav(`event-countdown`)"
    >
      Event Countdown
    </button>
    <button
      class="border-2 border-gray-500 px-4 py-2 rounded-full text-black bg-gray-200 hover:bg-gray-500 hover:text-white hover:border-white"
      @click="nav(`semester-week-num`)"
    >
      Semester Week Number
    </button>
  </div>
</template>
