<template>
    <footer>
        <div class="container mx-auto mt-20 xl:flex xl:justify-between xl:items-center xl:fixed xl:bottom-0 xl:mb-2">
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
    </footer>
</template>

<script setup>

import ContactFooter from './ContactFooter.vue';
import TextFooter from './TextFooter.vue';
import NavFooter from './NavFooter.vue';
import Icons from './Icons.vue';
import Copyright from './Copyright.vue'

</script>