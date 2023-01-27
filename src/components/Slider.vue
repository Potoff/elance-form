<template>
    <div class="mt-10 bg-gradient-to-r from-transparent to-yellow-600 rounded-xl shadow-xl flex flex-col justify-center content-center items-center">
        <div class="text-center text-lg font-medium w-full text-white text-bold">Votre prix : {{ props.value }}€/Wc</div>
        <input type="range" :disabled="true" class="w-full rounded-xl p-1 m-1" :value="props.value" min="0.01" max="5" step="0.01"/>
    </div>
</template>
  

<script setup>
import { ref } from 'vue';
const props = defineProps({
    value: Number
})



</script>

<style>

/********** Range Input Styles **********/
/*Range Reset*/
input[type="range"] {
   -webkit-appearance: none;
    appearance: none;
    background: white;
    opacity: 25%;
    cursor: pointer;
    width: 100%;
}

/* Removes default focus */
input[type="range"]:focus {
  outline: none;
}

/***** Chrome, Safari, Opera and Edge Chromium styles *****/
/* slider track */
input[type="range"]::-webkit-slider-runnable-track {
   background-color: transparent;
   border-radius: 0.5rem;
   height: 0.1rem;  
}

/* slider thumb */
input[type="range"]::-webkit-slider-thumb {
  -webkit-appearance: none; /* Override default look */
   appearance: none;
   margin-top: -12px; /* Centers thumb on the track */

   /*custom styles*/
   background-color: hsl(56, 96%, 27%);
   height: 1.5rem;
   width: 1.5rem;
   border-radius: 50%;
    padding-top: 2em;
}

input[type="range"]:focus::-webkit-slider-thumb {   
  border: 1px solid #053a5f;
  outline: 3px solid #053a5f;
  outline-offset: 0.125rem; 
}

/******** Firefox styles ********/
/* slider track */
input[type="range"]::-moz-range-track {
   background-color: transparent;
   border-radius: 0.5rem;
   height: 0rem;
}

/* slider thumb */
input[type="range"]::-moz-range-thumb {
   border: none; /*Removes extra border that FF applies*/
   border-radius: 0; /*Removes default border-radius that FF applies*/

   /*custom styles*/
   background-color: hsl(56, 96%, 27%);
   height: 1.5rem;
   width: 1.5em;
   border-radius: 50%;
}

input[type="range"]:focus::-moz-range-thumb {
  border: 1px solid #053a5f;
  outline: 3px solid #053a5f;
  outline-offset: 0.125rem; 
}

</style>