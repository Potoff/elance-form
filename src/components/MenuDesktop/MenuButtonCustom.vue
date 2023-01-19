<template>
    <Disclosure as="nav" v-slot="{ open }">
        <Menu as="div" class="relative ml-5">
            <!-- Mobile menu button-->
            <MenuButton>
                <DisclosureButton
                    class="inline-flex items-center justify-center rounded-md mr-3 text-gray-400 hover:bg-gray-500 hover:rounded-xl hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white">
                    <span class="sr-only">Open main menu</span>
                    <Bars3Icon v-if="!open" class="block h-6 w-6" aria-hidden="true" />
                    <XMarkIcon v-else class="block h-6 w-6" aria-hidden="true" />
                </DisclosureButton>
            </MenuButton>
            
                <NavItems />
            
        </Menu>
    </Disclosure>
</template>

<script setup>
import { Menu, MenuButton, MenuItem, MenuItems, Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue';
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import NavItems from './NavItems.vue';
</script>