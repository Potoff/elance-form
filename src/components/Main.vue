<template>
    <main>
        <div class="container mx-auto mt-20">
            <Title />
            <MainText />
            <QuoteForm @submit="FormSubmit">
            </QuoteForm>
            <Slider v-if="state.showSlider" :value="state.finalPrice">
            </Slider>
        </div>
    </main>
</template>

<script setup>

import Slider from './Slider.vue';
import Title from './Title.vue';
import MainText from './MainText.vue';
import QuoteForm from './QuoteForm.vue';
import { reactive } from 'vue';

let FormSubmit = (finalPrice) => {
    state.showSlider = true;
    state.finalPrice = finalPrice
    return   finalPrice;
}

let state = reactive({
    showSlider: false,
    finalPrice: 0
});


</script>