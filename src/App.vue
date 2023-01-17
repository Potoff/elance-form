<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavbarDesktop from './components/MenuDesktop/NavbarDesktop.vue';
import NavbarMobile from './components/MobileMenu/NavbarMobile.vue';
</script>

<template>
<NavbarDesktop />
<NavbarMobile />

<RouterView />
</template>

<style scoped>

</style>
