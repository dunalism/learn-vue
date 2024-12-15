<script setup>
import { ref } from "vue";

const text = ref("");
</script>

<template>
  <input v-model="text" placeholder="Type here" />
  <!-- v-model secara otomatis menyinkronkan nilai <input> dengan state terikat, jadi kita tidak perlu event handlers. -->
  <p>{{ text }}</p>
</template>
