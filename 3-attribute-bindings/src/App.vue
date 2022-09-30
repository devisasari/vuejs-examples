<!--
Here we are reactively binding element attributes / properties to the state.
The :title syntax is short for v-bind:title.
-->

<script setup>
import { ref } from "vue";

const message = ref("Vue harika!");
const isPurple = ref(true);
const color = ref("orange");

function togglePurple() {
  isPurple.value = !isPurple.value;
}

function toggleColor() {
  color.value = color.value === "orange" ? "yellow" : "orange";
}
</script>

<template>
  <p>
    <span :title="message">
      Bu projede attribute veya propertyleri dinamik olarak bağladım. Bu cümlenin yerinde
      başka bir mesaj vardı, koda bakabilirsiniz. Ancak ref() kullandığım için
      mesaj değişti. Ayrıca class ve style binding örneği yaptım.
    </span>
  </p>

  <!--
  class bindings have special support for objects and arrays
  in addition to plain strings
  -->
  <p :class="{ purple: isPurple }" @click="togglePurple">
    Bu cümleyi mor renge çevirmek için buraya tıkla.
  </p>

  <!-- style bindings also support object and arrays -->
  <p :style="{ color }" @click="toggleColor">
    Bu cümleyi turuncuya çevirmek için buraya tıkla, sonra da ister sarıya çevir
    ister turuncuya.
  </p>
</template>

<style>
.purple {
  color: purple;
}
</style>
