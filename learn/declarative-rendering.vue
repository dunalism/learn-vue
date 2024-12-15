<script setup>
import { reactive, ref } from "vue";
// Fitur inti Vue adalah rendering deklaratif:
// menggunakan sintaksis templat yang memperluas HTML, kita dapat menjelaskan bagaimana HTML seharusnya terlihat berdasarkan state JavaScript. Saat state berubah, HTML diperbarui secara otomatis.

const counter = reactive({ count: 0 });
const message = ref("Hello World!");

// Di Vue, ref digunakan untuk menyimpan nilai reaktif (seperti state lokal), sedangkan reactive digunakan untuk objek atau struktur data yang kompleks

// Jenis Data: reactive() hanya bekerja dengan objek, sedangkan ref() dapat bekerja dengan tipe data apapun.

// Akses Nilai: Nilai yang dibuat dengan ref() diakses melalui properti .value, sedangkan nilai yang dibuat dengan reactive() diakses langsung seperti objek biasa.
</script>

<template>
  <h1>{{ message }}</h1>
  <p>Count is: {{ counter.count }}</p>
</template>
