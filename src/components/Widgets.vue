<script setup>
import { ref } from 'vue';
import CardWidget from './CardWidget.vue';
import { TransitionRoot } from '@headlessui/vue'

const primaryCourses = [
    {title: 'English Level C1', subtitle: 'Stage 36/70', theme: 'bg-emerald-400'},
    {title: 'UI/UX design: Advanced', subtitle: 'Stage 37/121', theme: 'bg-cyan-500'},
]

const additionalCourses = [
    {title: 'Speaking Club', subtitle: '7:30-08:15', theme: 'bg-yellow-500'},
    {title: 'Create a cool portofolio', subtitle: '18:45-20:00', theme: 'bg-blue-500'},
]

let isShowing = ref(true)


</script>

<template>
    <div class="flex flex-col">
        <div class="text-3xl font-bold tracking-tight text-gray-900">
            Today
        </div>
        <TransitionRoot
            appear
            :show="isShowing"
            enter="transition-transform transition-opacity duration-500"
            enter-from="opacity-0 translate-y-10 scale-110"
            enter-to="opacity-100 scale-1"
        >
            <CardWidget title="Courses" :courses="primaryCourses"/>
            <CardWidget title="Additional" :courses="additionalCourses"/>
        </TransitionRoot>
    </div>
</template>