<script setup>
import { ref } from 'vue';

const emit = defineEmits(['update-input']);
const inputVakue = ref('');

const updateInput = () => {
  emit('update-input', inputVakue.value);
};
</script>

<template>
    <div>
        <input v-model="inputVakue" @input="updateInput" />
    </div>
</template>