<script setup>
import { ref, defineProps } from 'vue';

const emit = defineEmits(['increment']);
const count = ref(0);

const increment = () => {
  count.value++;
  emit('increment', count.value);
};
</script>

<template>
  <button @click="increment">Кількість: {{ count }}</button>
</template>

<style scoped>
button {
  padding: 10px 20px;
  font-size: 16px;
  border: 1px solid #000;
  border-radius: 5px;
  background-color: #fff;
  cursor: pointer;
}
</style>