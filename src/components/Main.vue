<template>
    <main>
        <div class="container mx-auto mt-20">
            <Title />
            <MainText />
            <QuoteForm @submit="FormSubmit">
            </QuoteForm>
            <Slider v-if="state.showSlider" :value="FormSubmit().price">
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

let state = reactive({
    showSlider: false
})

let FormSubmit = (finalPrice) => {
    state.showSlider = true;
    
    return  {price: finalPrice} ;
}

console.log(FormSubmit().price)

</script>