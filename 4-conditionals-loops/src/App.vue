<!--
We can render content conditionally or in a loop with the v-if and v-for directives.
-->

<script setup>
import { ref } from "vue";

const show = ref(true);
const list = ref([1, 2, 3, 4, 5, 6, 7]);
</script>

<template>
  <hr />
  <button @click="list.push(list.length + 1)">Listeye Sayı Ekle</button>
  <hr />
  <button @click="list.pop()">Listeden Sayı Çıkar</button>
  <hr />
  <button @click="list.reverse()">Listeyi Tersine Çevir</button>
  <hr />
  <button @click="show = !show">Listeyi Kapat/Aç</button>
  <hr />
  <ul v-if="show && list.length">
    <li v-for="item of list">{{ item }}</li>
  </ul>
  <p v-else-if="list.length">Liste boş değil ama gizli.</p>
  <p v-else>Liste boş.</p>
</template>
