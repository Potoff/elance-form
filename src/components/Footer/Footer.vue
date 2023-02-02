<template>
    <footer>
        <div>
            <div
                class="mx-auto w-full mt-20 w-lg xl:flex xl:justify-around xl:items-center xl:sticky xl:bottom-0 xl:mb-2">
                <div>
                    <TextFooter />
                    <ContactFooter />
                </div>
                <NavFooter class="order-last" />
                <div class="xl:mr-32">
                    <Icons />
                    <Copyright />
                </div>
            </div>
        </div>
    </footer>
</template>

<script setup>

import ContactFooter from './ContactFooter.vue';
import TextFooter from './TextFooter.vue';
import NavFooter from './NavFooter.vue';
import Icons from './Icons.vue';
import Copyright from './Copyright.vue'

</script>