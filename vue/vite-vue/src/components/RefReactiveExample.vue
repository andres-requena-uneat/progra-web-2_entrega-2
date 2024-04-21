<script setup>
  import { ref, reactive } from 'vue'

  const refInput = ref("")

  const isEdit = ref(false)

  const person = reactive({
    name: "Andres",
    surname: "Requena",
    age: 22,
    major: "Computer Science"
  })


</script>

<template>
  <h1>Ejemplos de Ref y Reactive</h1>

  <h2>Ejemplo de Ref</h2>

  <p>Lo que escribas aquí: <input type="text" v-model="refInput" /> </p>
  <p>Se mostrará acá: "{{ refInput }}"</p>


  <h2>Ejemplo de Reactive</h2>
  <p>Al Editar los campos, estos se almacenan y se muestran</p>

  <p>Perfil</p>
  <div v-if="!isEdit">
    <p>Nombre: {{ person.name }}</p>
    <p>Apellido: {{ person.surname }}</p>
    <p>Edad: {{ person.age }}</p>
    <p>Carrera: {{ person.major }}</p>
  </div>
  <div v-else>
    <p>Nombre: <input v-model="person.name" /></p>
    <p>Apellido: <input v-model="person.surname" /></p>
    <p>Edad: <input v-model="person.age" /></p>
    <p>Carrera: <input v-model="person.major" /></p>
  </div>
  <button @click="isEdit = !isEdit"> {{ isEdit ? "Guardar" : "Editar" }} </button>

  
</template>

<style lang="sass" scoped>

</style>