<script setup>
import { Disclosure, DisclosureButton, DisclosurePanel,} from '@headlessui/vue'
import { Bars3Icon,  XMarkIcon, AcademicCapIcon, ChatBubbleBottomCenterIcon, MagnifyingGlassIcon, InformationCircleIcon, CogIcon} from '@heroicons/vue/24/outline'

const navigation = [
  { name: 'Overview', href: '#', current: true },
  { name: 'Learn', href: '#', current: false },
  { name: 'Hub', href: '#', current: false },
  { name: 'Activity', href: '#', current: false },
  { name: 'Leaderboard', href: '#', current: false },
  { name: 'Comunity', href: '#', current: false },
  { name: 'Jobs', href: '#', current: false },
]

</script>

<template>
    <Disclosure as="nav" class="bg-gray-900 border-b-2 border-gray-500" v-slot="{ open }">
      <div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
        <div class="flex h-16 items-center justify-between">
          <div class="flex items-center">
            <div class="flex-shrink-0 text-white">
              <AcademicCapIcon class="h-8 w-8" aria-hidden="true" />
            </div>
            <div class="hidden md:block">
              <div class="ml-10 flex items-baseline space-x-4">
                <a v-for="item in navigation" :key="item.name" :href="item.href" :class="[item.current ? 'text-white' : 'text-gray-300 hover:text-white', 'px-3 py-2 rounded-md text-sm font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</a>
              </div>
            </div>
          </div>
          <div class="hidden md:block">
            <div class="ml-4 flex items-center md:ml-6 gap-2">
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <MagnifyingGlassIcon class="h-5 w-5" aria-hidden="true" />
              </button>        
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <ChatBubbleBottomCenterIcon class="h-5 w-5" aria-hidden="true" />
              </button>              
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <InformationCircleIcon class="h-5 w-5" aria-hidden="true" />
              </button>        
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <CogIcon class="h-5 w-5" aria-hidden="true" />
              </button>        
            </div>
          </div>
          <div class="-mr-2 flex md:hidden">
            <!-- Mobile menu button -->
            <DisclosureButton class="inline-flex items-center justify-center rounded-md bg-gray-800 p-2 text-gray-400 hover:bg-gray-700 hover:text-white focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
              <span class="sr-only">Open main menu</span>
              <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
              <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
            </DisclosureButton>
          </div>
        </div>
      </div>

      <!-- Mobile View -->
      <DisclosurePanel class="md:hidden">
        <div class="space-y-1 px-2 pt-2 pb-3 sm:px-3">
          <DisclosureButton v-for="item in navigation" :key="item.name" as="a" :href="item.href" :class="[item.current ? 'bg-gray-900 text-white' : 'text-gray-300 hover:bg-gray-700 hover:text-white', 'block px-3 py-2 rounded-md text-base font-medium']" :aria-current="item.current ? 'page' : undefined">{{ item.name }}</DisclosureButton>
        </div>
        <div class="border-t border-gray-700 pt-4 pb-3">
          <div class="flex items-center px-5">
            <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <MagnifyingGlassIcon class="h-5 w-5" aria-hidden="true" />
              </button>        
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <ChatBubbleBottomCenterIcon class="h-5 w-5" aria-hidden="true" />
              </button>              
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <InformationCircleIcon class="h-5 w-5" aria-hidden="true" />
              </button>        
              <button type="button" class="rounded-full bg-gray-700 p-2 text-gray-200 hover:text-white hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 focus:ring-offset-gray-800">
                <CogIcon class="h-5 w-5" aria-hidden="true" />
              </button>     
          </div>
          <div class="mt-3 space-y-1 px-2">
            <DisclosureButton v-for="item in userNavigation" :key="item.name" as="a" :href="item.href" class="block rounded-md px-3 py-2 text-base font-medium text-gray-400 hover:bg-gray-700 hover:text-white">{{ item.name }}</DisclosureButton>
          </div>
        </div>
      </DisclosurePanel>
    </Disclosure>
</template>

