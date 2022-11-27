
<script>
import { EllipsisHorizontalIcon } from '@heroicons/vue/24/outline'
import { ref } from 'vue'
import { TransitionChild, TransitionRoot } from '@headlessui/vue'


export default {
    components: {EllipsisHorizontalIcon, TransitionChild, TransitionRoot},
    setup() {

        let hours = [];
        for (let index = 0; index < 24; index++) {
            hours[index] = `${index.toString().padStart(2, '0')}:00`;   
        }
        
        const itemsCourses = [
            {id: 1, leftPosition: 200, title: 'Practice: Writing and Talking', subtitle: 'English level C1', theme: 'bg-emerald-400'},
            {id: 2, leftPosition: 760, title: 'Interface animation in Principle', subtitle: 'UI/UX Design: Advanced', theme: 'bg-cyan-500'},
        ]

        const itemsAdditional = [
            {id: 1, leftPosition: 400, title: 'Create a cool portofolio', subtitle: 'Group lecture', theme: 'bg-slate-100'},
        ]

        let dropZone = ref(null)

        function startDrag(event, item) {
            let element = event.target;
            // console.log(event)
        }
        

        function endDrag(event, item) {
            let element = event.target;
            let dropZoneScrollLeft = dropZone.value.scrollLeft
            let leftPosition = event.screenX+dropZoneScrollLeft-656;
            element.style.left = `${leftPosition}px`
            item.leftPosition = leftPosition
        }
        
        function onDrop(event) {
            let element = event.target;
            // console.log(event.offsetX)
        }

        return { dropZone, itemsCourses, itemsAdditional, hours, startDrag, endDrag, onDrop, EllipsisHorizontalIcon };
    }
}

</script>

<template>
    <div class="flex flex-col">
        <div class="text-3xl font-bold tracking-tight text-gray-900">
            Timetable
        </div>
        <TransitionRoot appear :show="true">
        <div 
        class="relative mt-10 h-[33rem] p-2 w-[118%] flex gap-56 scroll-smooth overflow-scroll overflow-y-hidden"
        ref="dropZone" 
        @drop="onDrop($event)" 
        @dragover.prevent
        @dragenter.prevent
        >
            <div v-for="(h) in hours" class="hour text-gray-400">
                {{h}}
            </div>
            <div class="absolute">
                <TransitionChild
                enter="transition-transform transition-opacity duration-500"
                enter-from="opacity-0 translate-y-10"
                enter-to="opacity-100"
                >
                <div 
                v-for="(item, i) in itemsCourses"
                :id="item.id"
                :class="[item.theme, 'lesson absolute w-52 border-2 rounded-md border-gray-500 p-3 mt-10 cursor-move']" 
                :style="{left: item.leftPosition+'px'}"
                draggable="true"
                @dragstart="startDrag($event, item)"
                @dragend="endDrag($event, item)"
                >
                    <div class="flex justify-between">
                        <div class="bg-white text-gray-800 rounded-2xl px-2">17:30-18:30</div>
                        <EllipsisHorizontalIcon class="h-5 w-5" aria-hidden="true" />
                    </div>
                    <div class="text-xl font-bold tracking-tight text-gray-900 mt-12">
                        {{ item.title }}
                    </div>
                    <div class="text-sm tracking-tight text-gray-700 my-2">
                        {{ item.subtitle }}
                    </div>
                </div>
                </TransitionChild>
            </div>
            <div class="absolute top-2/4 text-gray-400 w-full">Additional courses</div>
            <div class="absolute top-2/4">
                <TransitionChild
                enter="transition-transform transition-opacity duration-500"
                enter-from="opacity-0 translate-y-10"
                enter-to="opacity-100"
                >
                <div 
                v-for="(item, i) in itemsAdditional"
                :id="item.id"
                :class="[item.theme, 'lesson absolute w-52 border-2 rounded-md border-gray-500 p-3 mt-10 cursor-move']" 
                :style="{left: item.leftPosition+'px'}"
                draggable="true"
                @dragstart="startDrag($event, item)"
                @dragend="endDrag($event, item)"
                >
                    <div class="flex justify-between">
                        <div class="bg-white text-gray-800 rounded-2xl px-2">17:30-18:30</div>
                        <EllipsisHorizontalIcon class="h-5 w-5" aria-hidden="true" />
                    </div>
                    <div class="text-xl font-bold tracking-tight text-gray-900 mt-12">
                        {{ item.title }}
                    </div>
                    <div class="text-sm tracking-tight text-gray-700 my-2">
                        {{ item.subtitle }}
                    </div>
                </div>
                </TransitionChild>
            </div>
        </div>
        </TransitionRoot>
    </div>
</template>

<style scoped>
.hour:after{
    display: block;
    content: "";
    height: 28rem;
    width: 2px;
    margin-left: 1.1rem;
    background-color: rgb(208, 208, 208);
}

</style>
