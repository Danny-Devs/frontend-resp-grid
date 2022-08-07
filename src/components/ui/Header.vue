<script setup>

</script>

<template>
  <main pb-2 pt-6 px-6 flex items-center justify-between dark:text-gray-100>
    <div text-2xl i-carbon-camera />
    <div flex items-center>
      <div v-if="isDark" i-carbon-sun @click="toggleDark()" />
      <div v-if="!isDark" i-carbon-moon @click="toggleDark()" />
      <button ml-4 sm:ml-6 bg-black dark:bg-red-400 dark:text-white px-8 py-3 rounded-full text-xs sm:text-md class="text-[#FFF7F0]">
        Free Consultation
      </button>
    </div>
  </main>
</template>

<style scoped>

</style>
