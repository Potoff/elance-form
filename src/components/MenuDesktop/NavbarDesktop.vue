<template>

    <header>
        <div class="hidden xl:flex justify-between items-center container mx-auto">
            <MenuDesktop />
            <Logo />
            <ButtonConnexion />
        </div>
    </header>

</template> 

<script setup>

import ButtonConnexion from './ButtonConnexion.vue';
import MenuDesktop from './MenuDesktop.vue';
import Logo from '../Logo/Logo.vue';

</script>