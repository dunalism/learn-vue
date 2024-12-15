<script setup>
import { ref } from "vue";
import ChildComp from "./child.vue";

const childMsg = ref("No child msg yet");
const greeting = ref("Hello from parent");
</script>

<template>
  <ChildComp @response="(msg) => (childMsg = msg)" :msg="greeting" />
  <p>{{ childMsg }}</p>
</template>
