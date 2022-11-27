<template>
  <HeaderApp />
  <main class="mx-auto max-w-7xl py-10 px-4 sm:px-6 lg:px-8 flex gap-2">
    <div class="w-4/12">
      <Widgets />
    </div>
    <div class="w-8/12">
      <Timetable />
    </div>
  </main>
</template>

<script setup>
import HeaderApp from './components/Header.vue'
import Widgets from './components/Widgets.vue'
import Timetable from './components/Timetable.vue'
</script>