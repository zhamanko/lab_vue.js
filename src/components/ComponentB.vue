<script setup>
import { ref, onMounted, onBeforeUnmount } from 'vue';
import { eventBus } from '@/eventBus';

const message = ref('');

const handleMessage = (data) => {
  message.value = data;
};

onMounted(() => {
  eventBus.on('messageReceived', handleMessage);
});

onBeforeUnmount(() => {
  eventBus.listeners['messageReceived'] = eventBus.listeners['messageReceived'].filter(
    (listener) => listener !== handleMessage
  );
});
</script>

<template>
  <h2>{{ message }}</h2>
</template>
