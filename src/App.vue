<script setup>
const name = 'Marina'
const styleColor = 'color:pink'
//const arrayColor =["red","pink","ARG"] ejemplo con array,
const activo = false;
</script>
<!-- etiqueta template renderiza todo el html -->
<template>
  <h1 class="h1">Hola Soy {{ name.toUpperCase() }} Programadora FullStack 🌀</h1>
  <!--   <h2>{{ arrayColor }}</h2> muestra en texto el array -->
  <h2 :style="styleColor">Background en artes visuales</h2>
  <!-- v:bind:suplanta las {{  }} ///:style(abreviado)-->
 <!--  <h2>
    {{ activo ? "Estoy activo" : "No estoy activo" }}
  </h2> -->
  <h2 v-if="activo === true">Sigo...</h2> <!-- Directivas v-if ó v-else -->
  <h2  v-else-if="activo === false">Yo estoy activa igual</h2> <!-- directiva else tiene que estar seguido del if -->
<!--   <h2  v-if="!activo">Yo estoy activa igual</h2> -->
<h2  v-else>y si estas pensando yo sigo activa igual...</h2> 
</template>

<style>
h1 {
  color: blueviolet;
}
</style>
