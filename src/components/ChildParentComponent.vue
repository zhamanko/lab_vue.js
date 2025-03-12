<script setup>
import { inject } from 'vue';

const message = inject('message');
</script>

<template>
    <h3>{{ message }}</h3>
</template>