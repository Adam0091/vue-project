<script setup>
    defineProps({
        text: String
    })
</script>


<template>
    <button class="button">{{ text }}</button>
</template>

<style scoped>
    .button {
        padding: 10px;
    }
</style>