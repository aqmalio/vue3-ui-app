<script setup>

import { BugAntIcon, EllipsisHorizontalIcon } from '@heroicons/vue/24/outline';

const props = defineProps({
        title: { type: String, default: "Title" },
        subtitle: { type: String, default: "Subtitle" }
    })

</script>

<template>
    <div class="flex items-center py-4 justify-between">
        <div class="flex items-center">
            <slot></slot>
            <div class="flex flex-col px-4">
                <div class="text-sm font-bold text-gray-800">{{ title }}</div>
                <div class="text-sm font-medium text-gray-400">{{ subtitle }}</div>
            </div>
        </div>
        <EllipsisHorizontalIcon class="h-5 w-5" aria-hidden="true" />
    </div>
</template>