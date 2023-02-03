<template>
    <form @submit="formSubmit">
        <div class="mt-20 w-60 mx-auto">
            <div class="mb-3 rounded-xl shadow-lg bg-white">
                <input type="number" 
                :class="[state.btnDisabled ? ['border-2', 'border-red-500', 'focus:border-red-600'] : ['border-2', 'border-green-500', 'focus:border-green-600']]"
                class="
        mx-auto
        form-control
        block
        w-full
        px-3
        py-1.5
        text-base
        font-normal
        text-gray-700
        bg-gray-50
        rounded-xl
        transition
        ease-in-out
        m-0
      " id="exampleNumber0" placeholder="Prix TTC" min="0" max="100000" v-model="state.price" @input="validateNumber"/>
            </div>          
            <div class="mb-3 rounded-xl shadow-lg bg-white">
                <input type="number" 
                :class="[state.btnDisabled ? ['border-2', 'border-red-500', 'focus:border-red-600'] : ['border-2', 'border-green-500', 'focus:border-green-600']]"
                class="
        mx-auto
        form-control
        block
        w-full
        px-3
        py-1.5
        text-base
        font-normal
        text-gray-700
        bg-gray-50 
        rounded-xl
        transition
        ease-in-out
        m-0
        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
      " id="exampleNumber0" placeholder="Taille de l'installation" min="0" max="100000" v-model="state.size" @input="validateNumber"/>
            </div>
            <div class="text-center mt-10 text-red-500" v-if="state.errorMsg">
                <p>{{state.errorMsg}}</p>
            </div>
            <div class="text-center mt-10">
                <button type="submit"
                    class="inline-block px-6 py-2.5 bg-yellow-300 text-white font-medium text-xs leading-tight uppercase rounded-full "
                    :class="[!state.btnDisabled ? ['bg-yellow-500', 'shadow-md', 'hover:bg-yellow-600', 'hover:shadow-lg', 'focus:bg-yellow-600', 'focus:shadow-lg', 'focus:outline-none', 'focus:ring-0', 'active:bg-yellow-700', 'active:shadow-lg', 'transition', 'duration-150', 'ease-in-out'] : '']"
                    :disabled="state.btnDisabled"
                    >Vérifier        
                    mon devis
                </button>

            </div>
        </div>
    </form>
</template>

<script setup>

import { computed, ref, reactive } from 'vue';

let state = reactive({
    errorMsg: '',
    price: '',
    size: '',
    btnDisabled: true,
});



let validateNumber = (e) => {
    e.preventDefault();
    if (state.price < 1 || state.price > 100000 || state.size < 1 || state.size > 100000) {
        state.errorMsg = 'Merci de rentrer des chiffres correct.'
        state.btnDisabled = true
    } else {
        state.errorMsg = "";
        state.btnDisabled = false;
    }
};

let emit = defineEmits(['submit'])
function formSubmit(e){
    e.preventDefault();
    emit('submit', (state.price / (state.size * 1000)).toFixed(2))
};

</script>