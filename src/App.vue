<script setup>
import { ref } from 'vue';

import HelloWorld from './components/HelloWorld.vue';
import ButtonCounter from './components/ButtonCounter.vue';
import Card from './components/Card.vue';

const totalClicks = ref(0);

const incrementTotalClicks = (clicks) => {
  totalClicks.value = clicks;
};

</script>

<template>
  <div class="container">
    <HelloWorld name="Vue" />
    <br>
    <p>Загальна кількість кліків: {{ totalClicks }}</p>
    <br>
    <ButtonCounter @increment="incrementTotalClicks" />
    <br>
    <Card>
      <h2>Lorem, ipsum</h2>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit.</p>
    </Card>
  </div>
</template>

<style scoped>

</style>
