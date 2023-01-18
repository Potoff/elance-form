<template>
    <div class="flex xl:hidden">
        <div>
            <button
                class="inline-flex items-center justify-center rounded-md mr-3 text-gray-400 hover:bg-gray-500 hover:rounded-xl hover:text-white focus:outline-none focus:ring-2 focus:ring-inset focus:ring-white"
                type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasExample"
                aria-controls="offcanvasExample">
                <Bars3Icon class="block h-6 w-6" aria-hidden="true" data-bs-toogle="offcanvas"
                    data-bs-target="#offcanvasExample" aria-controls="offcanvasExample" />
            </button>

            <!-- Offcanvas component -->
            <div class="offcanvas offcanvas-start fixed bottom-0 flex flex-col max-w-full bg-white invisible bg-clip-padding shadow-sm outline-none transition duration-300 ease-in-out text-gray-700 top-0 left-0 border-none w-96"
                tabindex="-1" id="offcanvasExample" aria-labelledby="offcanvasExampleLabel">
                <div class="offcanvas-header flex items-center justify-between p-4">
                    <Logo /> 
                    <button type="button"
                        class="btn-close box-content w-4 h-4 p-2  mb-4 text-black border-none rounded-none opacity-50 focus:shadow-none focus:outline-none focus:opacity-100 hover:text-black hover:opacity-75 hover:no-underline"
                        data-bs-dismiss="offcanvas" aria-label="Close"></button>
                </div>
                <div class="offcanvas-body p-4">
                    <div class="flex flex-col">
                        <div>
                            <Disclosure as="nav" v-slot="{ open }">
                                <Menu as="div" class="">
                                    <NavItemsMobile />
                                </Menu>
                            </Disclosure>
                        </div>
                        <div>
                            <ButtonConnexion />
                        </div>
                        <div class="flex justify-evenly mt-8 mx-4">
                            <Facebook />
                            <Youtube />
                            <Instagram />
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>

import { Menu, MenuButton, MenuItem, MenuItems, Disclosure, DisclosureButton, DisclosurePanel } from '@headlessui/vue';
import { Bars3Icon, BellIcon, XMarkIcon } from '@heroicons/vue/24/outline'
import Logo from '../Logo/Logo.vue';
import NavItemsMobile from './NavItemsMobile.vue'
import ButtonConnexion from './ButtonConnexion.vue';
import Facebook  from '../icons/Facebook.vue';
import Youtube from '../icons/Youtube.vue';
import Instagram from '../icons/Instagram.vue';

 
</script>