<script setup>
import { eventBus } from '@/eventBus';

const sendMessage = () => {
  eventBus.emit('messageReceived', 'Привіт із ComponentA!');
};
</script>

<template>
  <button @click="sendMessage">Надіслати повідомлення</button>
</template>
