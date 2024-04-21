<script setup>
import { computed, ref, watch } from "vue"


  const num1 = ref(5)
  const num2 = ref(7)

  const computedAddition = computed(() =>  num1.value + num2.value)
  const computedSubtraction = computed(() =>  num1.value - num2.value)
  const computedMultiplication = computed(() =>  num1.value * num2.value)
  const computedDivision = computed(() =>  (num1.value / num2.value).toFixed(2))

  const counter = ref(0)

  watch(
    counter,
    (curr, prev) => {
      if (curr % 10 == 0) {
        alert(`El contador ha alcanzado un valor de ${curr}`)
      }
    }
  )


</script>

<template>
  <h1>Ejemplos de Watch y Computed</h1>

  <h2>Ejemplo de Computed</h2>
  Se calcula automaticamente cuando cambia alguna de las variables!
  <p>Numero1: <input type="number" v-model="num1"/></p>
  <p>Numero2: <input type="number" v-model="num2"/></p>
  <p>Suma : {{ computedAddition }}</p>
  <p>Resta : {{ computedSubtraction }}</p>
  <p>Multiplicacion : {{ computedMultiplication }}</p>
  <p>Division : {{ computedDivision }}</p>


  <h2>Ejemplo de Watch</h2>
  <p> cada vez que el contador alcance un multiplo de 10 se lanzara una alerta</p>
  <button @click="counter += 1"> Count: {{ counter }}</button>

  
</template>

<style scoped>

</style>