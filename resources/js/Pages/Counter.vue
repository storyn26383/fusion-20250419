<php>
    $count = prop(0);
    $doubleCount = prop(fn () => $count * 2)->readonly();
</php>

<template>
    <button @click="count++; fusion.sync()">
        <h1>Count: {{ count }}</h1>
    </button>
    <h1>Double Count: {{ doubleCount }}</h1>
</template>
