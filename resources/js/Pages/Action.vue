<php>
    expose(getHeader: fn () => request()->header('User-Agent'));
</php>

<script setup>
    import { ref } from 'vue'
    const result = ref('')
    async function getResult() { result.value = await getHeader() }
</script>

<template>
    <button @click="getResult">
        <h1>Get User Agent from Server</h1>
    </button>
    <h1 v-if="result">{{ result }}</h1>
</template>
