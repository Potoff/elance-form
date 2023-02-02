<template>
    <div class="mt-20 mb-20 flex justify-between items-center">
        <div>
            <h4 class="font-bold text-xl">Compte rendu technique du devis</h4>
            <p class="text-sm">profitez d'une expertise indépendante</p>
        </div>
        <div class="mb-3 rounded-xl shadow-lg bg-white w-60">
            <label for="report" class="mx-auto
            cursor-pointer
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
        border-2 border-yellow-400 focus:border-yellow-500
        hover:pointer">
                <div class="flex justify-between">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5"
                        stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round"
                            d="M7.5 7.5h-.75A2.25 2.25 0 004.5 9.75v7.5a2.25 2.25 0 002.25 2.25h7.5a2.25 2.25 0 002.25-2.25v-7.5a2.25 2.25 0 00-2.25-2.25h-.75m-6 3.75l3 3m0 0l3-3m-3 3V1.5m6 9h.75a2.25 2.25 0 012.25 2.25v7.5a2.25 2.25 0 01-2.25 2.25h-7.5a2.25 2.25 0 01-2.25-2.25v-.75" />
                    </svg>
                    <p class="text-center">Téléchargez votre devis</p>
                </div>
                <input type="file" class="hidden" id="report" />
            </label>
        </div>
    </div>
</template>

<script setup>

</script>