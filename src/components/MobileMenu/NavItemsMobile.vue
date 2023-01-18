<template>
    <transition enter-active-class="transition ease-out duration-100" enter-from-class="transform opacity-0 scale-95"
        enter-to-class="transform opacity-100 scale-100" leave-active-class="transition ease-in duration-75"
        leave-from-class="transform opacity-100 scale-100" leave-to-class="transform opacity-0 scale-95">
        <MenuItems static
            class="mt-1 w-48 focus:outline-none">
            <MenuItem v-slot="{ active }">
            <a href="#" 
            class="mb-2 text-lg"
            :class="[active ? 'bg-gray-100 rounded-lg' : '', 'block px-4 py-2 text-sm text-gray-700']">Potentiel
                solaire</a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
            <a href="#" 
            class="mb-2 text-lg"
            :class="[active ? 'bg-gray-100 rounded-lg' : '', 'block px-4 py-2 text-sm text-gray-700']">Questions 
                Réponses</a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
            <a href="#" 
            class="mb-2 text-lg"
            :class="[active ? 'bg-gray-100 rounded-lg' : '', 'block px-4 py-2 text-sm text-gray-700']">Installateurs
                locaux</a>
            </MenuItem>
            <MenuItem v-slot="{ active }">
            <a href="#" 
            class="text-lg"
            :class="[active ? 'bg-gray-100 rounded-lg' : '', 'block px-4 py-2 text-sm text-gray-700']">La carte
                solaire</a>
            </MenuItem>
        </MenuItems>
    </transition>
</template>

<script setup>
import { MenuItem, MenuItems } from '@headlessui/vue';

</script>