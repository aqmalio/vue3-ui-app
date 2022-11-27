<script>
import { TransitionChild, TransitionRoot } from '@headlessui/vue'

export default {
    components: { TransitionRoot, TransitionChild },
    props: {
        isActive: Boolean,
        items: Array,
        d: Number,
        day: String
    }
}
</script>

<template>
    <div class="relative p-5">
        <TransitionRoot appear :show="true">
        <div class="absolute w-[3px] h-5/6 bg-gray-600 -bottom-6">
            <TransitionChild
                enter="transition-transform transition-opacity duration-500"
                enter-from="opacity-0 translate-y-10 -scale-50"
                enter-to="opacity-100 scale-1"
            >
                <div :class="[isActive ? 'bg-white border-gray-400' : 'bg-gray-900 border-gray-100', 'h-4 w-4 -ml-1.5 mb-1  border-2 rounded-full animate-bounce']"></div>
            </TransitionChild>
            <TransitionChild
                v-for="(item, i) in items" 
                enter="transition-transform duration-500 delay-300"
                enter-from="opacity-0 translate-y-10 -scale-50"
                enter-to="opacity-100 scale-1"
            >
            <div :class="[item, 'h-3 w-3 -ml-[4.5px] mb-1 rounded-full animate-bounce']"></div>
            </TransitionChild>
        </div>
        <div class="flex flex-col gap-3 ml-6">
            <TransitionChild
                enter="transition-opacity duration-500 delay-200"
                enter-from="opacity-0 translate-y-10"
                enter-to="opacity-100 scale-1"
            >
            <span :class="[isActive ? 'text-white' : 'text-gray-500', 'text-7xl font-medium']">{{ d }}</span>
            </TransitionChild>
            <TransitionChild
                enter="transition-opacity duration-500 delay-200"
                enter-from="opacity-0 translate-y-10"
                enter-to="opacity-100 scale-1"
            >
            <span :class="[isActive ? 'text-white' : 'text-gray-500', 'text-2xl']">{{ day }}</span>
            </TransitionChild>
        </div>
        </TransitionRoot>
    </div>
</template>