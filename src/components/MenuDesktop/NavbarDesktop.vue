<template>

    <header>
        <div class="flex invisible xl:visible">
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