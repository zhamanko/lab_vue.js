<script setup>
import { ref } from "vue";

const helloMessage = ref("Hello, Vue 3!");
const text = ref("lorem ipsum dolor sit amet consectetur adipisicing elit sed do eiusmod tempor incididunt ut labore et dolore magna aliqua");
const year = ref(new Date().getFullYear());

let imageSrc = ref("https://picsum.photos/200/300");
const imageAlt = ref("Random image");

const changeImage = () => {
  imageSrc.value = "https://picsum.photos/200/300?random=" + Math.random();
};
</script>

<template>
  <div>
    <h1>{{ helloMessage }}</h1>
    <p>{{ text }}</p>
    <img :src="imageSrc" :alt="imageAlt">
    <br>
    <button @click="changeImage">Change image</button>
    <p>{{ year }}</p>
  </div>
</template>

<style scoped>
  div {
    text-align: center;
  }
  button {
    padding: 20px;
    border: none;
    border-radius: 20px;
    color: white;
    background-color: rgb(80, 27, 139);
  }
  img {
    border-radius: 0px 20px 0px 20px;
  }
</style>
