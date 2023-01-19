<script setup>
import { RouterLink, RouterView } from 'vue-router'
import NavbarDesktop from './components/MenuDesktop/NavbarDesktop.vue';
import NavbarMobile from './components/MobileMenu/NavbarMobile.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer/Footer.vue';
</script>

<template>
<NavbarDesktop />
<NavbarMobile />
<Main />
<Footer />


</template>

<style scoped>

</style>
