<script setup>
const name = 'Marina'
const styleColor = 'color:pink'
//const arrayColor =["red","pink","ARG"] ejemplo con array,
const activo = true;
</script>
<!-- etiqueta template renderiza todo el html -->
<template>
  <h1 class="h1">Hola Soy {{ name.toUpperCase() }} Programadora FullStack 🌀</h1>
  <!--   <h2>{{ arrayColor }}</h2> muestra en texto el array -->
  <h2 :style="styleColor">Background en artes visuales</h2>
  <!-- v:bind:suplanta las {{  }} ///:style(abreviado)-->
  <h2>
    {{ activo ? "Estoy activo" : "No estoy activo" }}
  </h2>
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
