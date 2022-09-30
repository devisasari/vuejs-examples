<!-- Say Hello World with Vue! -->

<script setup>
import { ref } from 'vue'

// A "ref" is a reactive data source that stores a value.
// It's like a "let" in JavaScript.
const message = ref('Hello World!')
</script>

<template>
  <h1>{{ message }}</h1>
</template>