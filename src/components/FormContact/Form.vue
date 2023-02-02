<template>
    <div class="mb-10">
        <h4 class="font-bold text-xl">Déterminez votre production photovoltaïque</h4>
        <p class="text-sm">calcul de votre production réelle (en kWh) du devis</p>
    </div>
    <div class="flex flex-col items-center xl:flex xl:items-center xl:justify-start xl:flex-row">
        <div>
            <form class="flex flex-col items-center xl:inline">
                <legend class="text-xs">
                    Vous recevrez l'évaluation de votre ensoleillement sous 24 heures par courriel
                </legend>
                <div class="mt-10 w-60">
                    <div class="mb-3 rounded-xl shadow-lg bg-white">
                        <input type="text" class="
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
        border-2 border-gray-200
        m-0
      " id="exampleNumber0" placeholder="Votre nom" />
                    </div>
                    <div class="mb-3 rounded-xl shadow-lg bg-white">
                        <input type="email" class="
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
        border-2 border-gray-200
        m-0
        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
      " id="exampleNumber0" placeholder="Votre email" />
                    </div>
                    <div class="mb-3 rounded-xl shadow-lg bg-white">
                        <input type="text" class="
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
        border-2 border-gray-200
        m-0
        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
      " id="exampleNumber0" placeholder="Votre adresse postale" />
                    </div>
                    <div class="flex mt-5 items-center">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="w-4 h-4">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="M15 10.5a3 3 0 11-6 0 3 3 0 016 0z" />
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="M19.5 10.5c0 7.142-7.5 11.25-7.5 11.25S4.5 17.642 4.5 10.5a7.5 7.5 0 1115 0z" />
                        </svg>
                        <p class="text-xs mx-1">Confirmer l'emplacement avec la balise</p>
                    </div>
                    <div class="flex items-center mt-2">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                            stroke="currentColor" class="w-4 h-4">
                            <path stroke-linecap="round" stroke-linejoin="round"
                                d="M16.5 10.5V6.75a4.5 4.5 0 10-9 0v3.75m-.75 11.25h10.5a2.25 2.25 0 002.25-2.25v-6.75a2.25 2.25 0 00-2.25-2.25H6.75a2.25 2.25 0 00-2.25 2.25v6.75a2.25 2.25 0 002.25 2.25z" />
                        </svg>

                        <p class="text-xs mx-1">Informations aucunement partagées par élance</p>
                    </div>
                    <div class="mt-2 flex justify-start items-center">
                        <Switch v-model="enabled" :class="enabled ? 'bg-yellow-700' : 'bg-yellow-500'"
                            class="mr-2 relative inline-flex h-[14px] w-[32px] shrink-0 cursor-pointer rounded-full border-2 border-transparent transition-colors duration-200 ease-in-out focus:outline-none focus-visible:ring-2 focus-visible:ring-white focus-visible:ring-opacity-75"
                            @click="showTel">
                            <span class="sr-only">Use setting</span>
                            <span aria-hidden="true" :class="enabled ? 'translate-x-4' : 'translate-x-0'"
                                class="pointer-events-none inline-block h-[10px] w-[12px] transform rounded-full bg-white shadow-lg ring-0 transition duration-200 ease-in-out" />
                        </Switch>
                        <p class="text-xs">{{ phoneMessage }}</p>
                    </div>
                    <div v-if="showNumber" class="mb-3 rounded-xl shadow-lg bg-white mt-4">
                        <input type="tel" class="
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
        border-2 border-gray-200
        m-0
        focus:text-gray-700 focus:bg-white focus:border-blue-600 focus:outline-none
      " id="exampleNumber0" placeholder="Votre numéro de téléphone" />
                    </div>
                    <div class="text-center mt-10 text-red-500">
                        <p></p>
                    </div>
                    <div class="text-center mt-10">
                        <button type="submit"
                            class="inline-block px-6 py-2.5 bg-yellow-300 text-white font-medium text-xs leading-tight uppercase rounded-full ">Calcul
                            de la production d'électricité
                        </button>

                    </div>
                </div>
            </form>
        </div>
            <Map>
            </Map>
    </div>
</template>

<script setup>

import { ref } from 'vue'
import { Switch } from '@headlessui/vue'
import Map from './Map.vue';

const enabled = ref(false)
const showNumber = ref(true)
const phoneMessage = ref('je souhaite être rappelé')


let showTel = () => {
    if (!showNumber.value) {
        showNumber.value = true
        phoneMessage.value = 'je souhaite être rappelé'
    } else {
        showNumber.value = false
        phoneMessage.value = 'je ne souhaite pas être rappelé'
    }
}

</script>