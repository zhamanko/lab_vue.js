<script setup>
import { ref, provide } from 'vue';
import { useCounterStore } from './store/counter';

import ParentComponent from './components/ParentComponent.vue';
import ChildComponent from './components/ChildComponent.vue';
import ChildInputComponent from './components/ChildInputComponent.vue';
import ComponentA from './components/ComponentA.vue';
import ComponentB from './components/ComponentB.vue';

const message = 'Hello, Vue 3!';
const userInput = ref('');
const store = useCounterStore();

const updateMessage = (value) => {
  userInput.value = value;
};

provide('message', 'Дані з App.vue');
</script>

<template>
  <ChildComponent :text="message" />
  <br>
  <h2>Введений текст: {{ userInput }}</h2>
  <ChildInputComponent @update-input="updateMessage" />
  <br>
  <ParentComponent />
  <br>
  <h3>Кількість кліків: {{ store.count }}</h3>
  <button @click="store.increment">Додати</button>
  <br>
  <ComponentA />
  <ComponentB />
</template>

<style scoped>

</style>
