<script setup>
import FillContactes from './components/FillContactes.vue'
import {ref, reactive} from 'vue'
const llistaContactes=reactive([])
const nomContacte= ref('')
const telefonContacte= ref('')
const afegirContacte=()=>{
  llistaContactes.push({
  nom:String=nomContacte,
  telefon:String=telefonContacte
})
}
</script>

<template>
  <main>
  <h1>Llibreta de Contactes</h1>
  <input type="text" v-model="nomContacte" placeholder="Nom contacte">
  <input type="text" v-model="telefonContacte" placeholder="Numero de telefon">
  <button @click="afegirContacte">Afegir contacte</button>
  <FillContactes :llistaContactesFill="llistaContactes"/>


  </main>
</template>

<style scoped>
</style>
