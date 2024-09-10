<script setup>
const timer = ref("Loading...");

onMounted(() => {
  const countDownDate = new Date("December 05, 2024 23:59:59").getTime();

  const countdownFunction = setInterval(() => {
    const now = new Date().getTime();
    const distance = countDownDate - now;

    const months = Math.floor(distance / (1000 * 60 * 60 * 24 * 30));
    const days = Math.floor(
      (distance % (1000 * 60 * 60 * 24 * 30)) / (1000 * 60 * 60 * 24)
    );
    const hours = Math.floor(
      (distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)
    );
    const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((distance % (1000 * 60)) / 1000);

    if (distance < 0) {
      clearInterval(countdownFunction);
      timer.value = "EXPIRED";
    } else {
      // timer.value = `${months}M ${days}d ${hours}h ${minutes}m ${seconds}s`;
      timer.value = `${months}M ${days}d ${hours}h ${minutes}m`;
    }
  }, 1000);
});
</script>

<template>
  <div class="flex h-screen">
    <div
      class="flex w-screen h-screen rounded-lg border-4 border-[#3c6650] bg-[#243d30]"
    >
      <div class="flex flex-col justify-center items-center w-full">
        <div class="uppercase text-xl font-mono font-bold text-gray-400">
          Semester Ends
        </div>
        <div class="text-2xl font-mono font-bold text-white mt-4">
          {{ timer }}
        </div>
      </div>
    </div>
  </div>
</template>
