<script setup>
import { ref, onMounted } from "vue";

const weekNumber = ref("Loading...");

const ordinalNum = ["st", "nd", "rd"];

const getOrdinalSuffix = (number) => {
  const lastDigit = number % 10;
  const lastTwoDigits = number % 100;

  if (lastTwoDigits >= 11 && lastTwoDigits <= 13) {
    return `${number}th`;
  }

  switch (lastDigit) {
    case 1:
      return `${number}st`;
    case 2:
      return `${number}nd`;
    case 3:
      return `${number}rd`;
    default:
      return `${number}th`;
  }
};

onMounted(() => {
  const countDownDate = new Date("August 19, 2024 23:59:59").getTime();

  const updateWeekNumber = () => {
    const now = new Date().getTime();
    const distance = now - countDownDate;

    if (distance < 0) {
      weekNumber.value = "0th";
    } else {
      // Calculate the passed time in weeks and append the appropriate suffix
      const weeks = Math.ceil(distance / (1000 * 60 * 60 * 24 * 7)) + 1;
      weekNumber.value = getOrdinalSuffix(weeks) + " Week";
    }
  };

  // // Update once when mounted
  updateWeekNumber();

  // // Update every second
  // const countdownFunction = setInterval(updateWeekNumber, 1000);
});
</script>

<template>
  <div class="flex h-screen">
    <div
      class="flex flex-col w-screen h-screen rounded-lg border-4 border-[#3c6650] bg-[#243d30]"
    >
      <div
        class="flex p-2 justify-center text-xl font-mono font-bold text-white bg-[#1a2b22]"
      >
        Week #
      </div>
      <div class="flex flex-col justify-center items-center w-full h-full">
        <div class="text-2xl font-mono font-bold text-white mt-4">
          {{ weekNumber }}
        </div>
      </div>
    </div>
  </div>
</template>
