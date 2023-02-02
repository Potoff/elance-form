<template>
    <main>
        <div class="container mx-auto mt-20 lg:px-60 px-10">
            <Title />
            <MainText />
            <QuoteForm @submit="FormSubmit">
            </QuoteForm>
            <Slider v-if="state.showSlider" :value="state.finalPrice" :color="state.color" :thumb="state.thumb">
            </Slider>
            <Message v-if="state.showMessage" :value="state.finalPrice" :text="state.message" :color="state.color">
            </Message>
            <CalculButton v-if="state.showButton" @click="showRest">
            </CalculButton>
            <FormContact v-if="state.showFormContact">
            </FormContact>
        </div>
    </main>
</template>

<script setup>
import FormContact from './FormContact/FormContact.vue';
import CalculButton from './CalculButton.vue';
import Message from './Message.vue';
import Slider from './Slider.vue';
import Title from './Title.vue';
import MainText from './MainText.vue';
import QuoteForm from './QuoteForm.vue';
import { reactive } from 'vue';

let FormSubmit = (finalPrice) => {
    state.showSlider = true;
    state.showMessage = true;
    state.showButton = true;
    state.finalPrice = finalPrice;
    if (finalPrice < 2) {
        state.message = "Le prix n’est pas complet, vérifiez votre devis"
        state.color = 'text-blue-400'
        state.thumb = 'blue'
    }
    else if (finalPrice > 2 && finalPrice < 4) {
        state.message = "Prix normal du marché, essayez de réduire le prix"
        state.color = "text-green-500"
        state.thumb = "green"
    }
    else if (finalPrice > 4 && finalPrice < 5) {
        state.message = "Le prix de votre devis est élevé"
        state.color = "text-orange-500"
        state.thumb = "orange"
    } else {
        state.message = "Ce devis est hors de prix"
        state.color = "text-red-500"
        state.thumb = "red"
    }
    return finalPrice;
}

let showRest = () => {
    state.showFormContact = true
}

let state = reactive({
    showSlider: false,
    showMessage: false,
    showButton: false,
    showFormContact: false,
    finalPrice: 0,
    message: '',
    color: '',
    thumb: ''
});


</script>