<script setup>
import DateItem from './DateItem.vue'

const dates = [
    { d: 9, day: 'Monday', isActive: false, items: ['bg-red-200','bg-cyan-200'] },
    { d: 10, day: 'Tuesday', isActive: true, items: ['bg-amber-200'] },
    { d: 11, day: 'Wednesday', isActive: false, items: ['bg-yellow-200', 'bg-red-200','bg-green-200'] },
    { d: 12, day: 'Thursday', isActive: false, items: ['bg-lime-200', 'bg-cyan-200'] },
    { d: 13, day: 'Friday', isActive: false, items: ['bg-green-200', 'bg-indigo-200'] },
    { d: 14, day: 'Saturday', isActive: false, items: ['bg-cyan-200', 'bg-yellow-200'] }
]
</script>

<template>
    <div class="flex gap-10 flex-grow justify-between">
        <DateItem v-for="(date, i) in dates" 
            :isActive="date.isActive" 
            :d="date.d" 
            :day="date.day" 
            :items="date.items" />
    </div>
</template>