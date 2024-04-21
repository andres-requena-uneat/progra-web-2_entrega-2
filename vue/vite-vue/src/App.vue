<script setup>
import {ref} from 'vue'
import RefReactiveExample from './components/RefReactiveExample.vue';
import WatchComputedExample from './components/WatchComputedExample.vue';

const switcher = ref(false)


</script>

<template>
  <p><button @click="switcher = !switcher"> Mostrar ejemplo de  {{ switcher ? "Watch y Computed" : "Ref y Reactive" }}</button></p>

  <RefReactiveExample v-if="switcher" />
  <WatchComputedExample v-else />
  <footer>
    <div class="footer">
      <p>Andrés E. Requena G.</p>
      <p>72346798E</p>
      <p>Programación Web II</p>
    </div>
  </footer>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
.footer {
  background-color: #e0e0e0;
  height: 40px;
  width: 100%;
  position: fixed;
  top: 100%;
  left: 0;
  transform: translateY(-40px);
  display: flex;
  align-items: center;
  justify-content: space-evenly;
}
</style>
