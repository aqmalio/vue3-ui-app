<script setup>

import { CubeIcon, EllipsisHorizontalIcon } from '@heroicons/vue/24/outline';
import CardListItem from './CardListItem.vue';

const props = defineProps({
        title: { type: String, default: "Widget" },
        courses: { type: Object }
    })
</script>

<template>
    <div class="mt-10">
        <div class="text-sm font-bold  text-gray-500">{{ title }}</div>
        <div class="bg-white py-3 px-4 shadow sm:rounded-lg my-2 border-2 border-gray-100">
            <CardListItem v-for="(course, i) in courses" :title="course.title" :subtitle="course.subtitle">
                    <div :class="[course.theme, 'rounded-full p-3 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800']">
                        <CubeIcon class="h-5 w-5" aria-hidden="true" />
                    </div> 
            </CardListItem>   
        </div>
    </div>
</template>