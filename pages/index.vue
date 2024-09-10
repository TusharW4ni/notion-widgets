<script setup>
async function navigateToEventCounter() {
  await navigateTo("/event-countdown");
}
</script>

<template>
  <div class="flex h-screen justify-center items-center">
    <button
      v-on:click="navigateToEventCounter()"
      class="border p-2 rounded bg-gray-100 hover:bg-gray-300 hover:shadow-lg"
    >
      Event Counter
    </button>
  </div>
</template>
