<script setup lang="ts">
import { ref } from 'vue'

const PAGES = [1, 2, 3, 4, 5, 6, 7, 8, 9]

const selectedPage = ref(2)
const isStretch = ref(false)

const changePage = (page: number) => {
  selectedPage.value = page
  isStretch.value = false
}

</script>
<template>
  <div class="h-screen bg-gray">
    <div class="w-full p-4 flex justify-end fixed bottom-0">
      <div :class="{ 'w-[68px]': !isStretch, 'w-full': isStretch }" class="duration-1000">
        <div class="bg-white text-[14px] rounded-3xl">
          <div class="flex justify-around p-3 overflow-y-hidden">
            <template v-if="isStretch">
              <span v-for="page in PAGES" :key="page" class="cursor-pointer"
                :class="{ 'font-bold': page === selectedPage }" @click="changePage(page)"> {{ page }} </span>
              <span class="h-[22px] cursor-pointer" @click="isStretch = false">&gt;</span>
            </template>
            <template v-else>
              <span class="h-[22px] cursor-pointer" @click="isStretch = true">&lt;</span>
              <span>{{ selectedPage }}</span>
            </template>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
