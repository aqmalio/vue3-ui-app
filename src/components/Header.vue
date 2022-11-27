<script setup>
import { ChevronLeftIcon, ChevronRightIcon, CakeIcon} from '@heroicons/vue/24/outline'
import Menus from './Menu.vue'
import DateList from './DateList.vue'
</script>

<template>
<div class="min-h-full">
    
    <Menus />

    <header class="bg-gray-900 shadow">
      <div class="mx-auto max-w-7xl py-6 px-4 sm:px-6 lg:px-8 flex gap-2">
        <h1 class="text-3xl font-bold tracking-tight text-white">May 2022</h1>
        <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
          <CakeIcon class="h-5 w-5" aria-hidden="true" />
        </button>   
      </div>
      <div class="mx-auto max-w-7xl pb-6 px-4 sm:px-6 lg:px-8 flex gap-2 items-center">
        <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
          <ChevronLeftIcon class="h-5 w-5" aria-hidden="true" />
        </button>
        <DateList />
        <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
          <ChevronRightIcon class="h-5 w-5" aria-hidden="true" />
        </button>
      </div>
    </header>
  </div>
</template>

<style scoped>

</style>
