<script setup>
import {ref, computed} from 'vue';
const name = 'Marina'
const styleColor = 'color:pink'
//const arrayColor =["red","pink","ARG"] ejemplo con array,
const activo = true
const arrayFrutas = ['🍎', '🍌', '🍉', '🟠', '🍓']
const otherArray = [
  {
    name: 'Manzana',
    price: '5000',
    description: 'Una linda Manzanita'
  },
  {
    name: 'Banana',
    price: '7000',
    description: 'Banana come monito'
  },
  {
    name: 'Naranja',
    price: '9000',
    description: 'Vitamina C'
  }
]

const objectoFruta = {
  name: 'Banana',
  price: '7000',
  description: 'Banana come monito'
}

const newArray = [ /* usar directiva que traiga stock superior a 0 */
  {
    name: 'Manzana',
    price: '5000',
    description: 'Una linda Manzanita',
    stock:0,
  },
  {
    name: 'Banana',
    price: '7000',
    description: 'Banana come monito',
    stock:20,
  },
  {
    name: 'Naranja',
    price: '9000',
    description: 'Vitamina C',
    stock:10,
  }
]

const arrayFavoritos = ref([]);

// methods

const handleClick = (message) => {
  console.log(message)
}
const counter = ref (0);



const increment = () => {
//console.log('aumentar en cada click')
counter.value++ 
//console.log(counter)
}

const decrement = () => counter.value--
const reset = () => counter.value = 0

const classCounter = computed(() => {
  if (counter.value === 0) {
    return "zero";
  } else if (counter.value > 0) {
    return "positive";
  } else {
    return "negative";
  }
});

const add = () => { 
  arrayFavoritos.value.push(counter.value)
 }

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
  <h2 v-if="activo === true">Sigo...</h2>
  <!-- Directivas v-if ó v-else -->
  <h2 v-else-if="activo === false">Yo estoy activa igual</h2>
  <!-- directiva else tiene que estar seguido del if -->
  <!--   <h2  v-if="!activo">Yo estoy activa igual</h2> -->
  <h2 v-else>y si estas pensando yo sigo activa igual...</h2>

  <h2 v-show="activo">
    <!-- directiva v-show utiliza display:none si es false //se utiliza para alternar algo con mucha frecuencia -->
    Hola soy v-show
  </h2>

  <ul>
    <li v-for="(fruta, index) in arrayFrutas" :key="index">{{ index }} - {{ fruta }}</li>
    <!-- :key="id" para recorrer el array en vue se puede usar tanto in como of -->
  </ul>
  <ul>
    <li v-for="(string, i) in otherArray" :key="i">{{ string.name }} -{{ string.description }}</li>
  </ul>

  <ul>
    <li v-for="(value, propiedad, index) in objectoFruta" :key="value"> {{ index }}-{{ propiedad }} : {{ value }}</li> <!-- en este caso me renderiza todos los value del object -->
    
  </ul>

  <ul>
    <template v-for="item in newArray" :key="item.name"><!-- como utilizar un <> -->
     <li v-if="item.stock > 0">{{ item.name }}-{{ item.description }}</li><!-- v-if condicional dentro de la iteración -->
    </template>
  </ul>


  <button v-on:click.right.prevent="handleClick ('Texto right')"> 
    Activame right
  </button>

   <button @click="handleClick ('Texto 2')">
    Activame 2
  </button>
<h2 :class="classCounter">{{ counter }}</h2>
  <button @click="increment">
    Increment
  </button>

  <button @click="decrement">
    Decrement
  </button>

  <button @click="reset">
    Reset
  </button>

  <!-- <button :disabled="true">Add</button>  --><!-- disabled true desactive button -->

  <button @click="add">Add</button>
  <br>
  {{ arrayFavoritos }}
</template>

<style>
h1 {
  color: blueviolet;
}
.positive {
  color:green;
}

.negative {
  color:red;
}
.zero {
  color:purple;
}
</style>

{/* se puede poner v-on ó @click  */}
{/* modificadores en eventos */}
{/* reactividad en vue */}
{/* ref() una forma de trabajar con vue en la reactividad */}
anfn hacemos funcion flecha const funcionFlecha = anfn (aparece funcion flecha por extensión de ES7)


