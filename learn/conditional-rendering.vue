<script setup>
import { ref } from "vue";

const awesome = ref(true);

function toggle() {
  awesome.value = !awesome.value;
}
</script>

<template>
  <!-- We can also use v-else and v-else-if to denote other branches of the condition -->
  <button @click="toggle">Toggle</button>
  <h1 v-if="awesome">Vue is awesome!</h1>
  <h1 v-else>Oh no 😢</h1>
</template>
