<script setup lang="ts">

const pages = [1, 2, 3, 4, 5, 6, 7, 8, 9]

</script>
<template>
  <div class="h-screen bg-gray">
    <div class="w-full fixed bottom-[30px] px-4">
      <div class="w-full flex justify-around py-3 pl-3 bg-white rounded-3xl">
        <span v-for="page in pages" :key="page"> {{ page }} </span>
        <span class="h-[22px]">></span>
      </div>
    </div>
  </div>
</template>
<style scoped></style>
