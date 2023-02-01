<template>
<div class="text-center mt-4">
    <p :class="props.color" class="font-bold text-lg">{{ props.text }}</p>
</div>
</template>

<script setup>

const props = defineProps({
    value: Number,
    text: String,
    color: String
})



</script>