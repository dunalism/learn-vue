<script setup>
import { ref, onMounted } from "vue";

const pElementRef = ref(null);
import { ref, watch } from "vue";

const count = ref(0);

watch(count, (newCount) => {
  // yes, console.log() is a side effect
  console.log(`new count is: ${newCount}`);
});

onMounted(() => {
  pElementRef.value.textContent = "mounted!";
});
</script>

<template>
  <p ref="pElementRef">Hello</p>
</template>
