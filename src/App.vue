<script setup>

const name = "Marina";
const styleColor = "color:pink"
</script>
<!-- etiqueta template renderiza todo el html -->
<template>
  <h1 class="h1">Hola Soy {{name}} Programadora FullStack 🌀  </h1>
  <h2 v-bind:style="styleColor">Background en artes visuales</h2> <!-- v:bind:suplanta las {{  }} -->
</template>

<style>
h1 {
  color:blueviolet,
  
}
</style>
