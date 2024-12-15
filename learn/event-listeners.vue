<script setup>
import { ref } from "vue";

const count = ref(0);

function increment() {
  // update component state
  count.value++;
}
</script>

<template>
  <!-- @click is shorthand v-on:click  -->
  <button @click="increment">Count is: {{ count }}</button>
</template>
