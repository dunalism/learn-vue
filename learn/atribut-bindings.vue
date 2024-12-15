<script setup>
import { ref } from "vue";

const titleClass = ref("title");
</script>

<template>
  <!-- Di Vue, kita menggunakan binding data (v-bind atau :) untuk menghubungkan variabel dengan atribut atau konten elemen. -->
  <h1 :class="titleClass">Make me red</h1>
</template>

<style>
.title {
  color: red;
}
</style>
