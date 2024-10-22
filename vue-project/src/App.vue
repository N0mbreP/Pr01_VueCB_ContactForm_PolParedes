<script setup>
import FillContactes from './components/FillContactes.vue'
import {ref,computed} from 'vue'
const llistaContactes=ref([])
const nomContacte= ref('')
const telefonContacte= ref('')
const filtre= ref('')
const filtreResult=computed(()=>{
  return llistaContactes.value.filter(contacte=> contacte.nom.toLowerCase().includes(filtre.value.toLocaleLowerCase()))
})
const afegirContacte=()=>{
  llistaContactes.value.push({
  id:Date.now(),
  nom:nomContacte.value,
  telefon:telefonContacte.value
})
}
</script>

<template>
  <main>
  <h1>Llibreta de Contactes</h1>
  <input type="text" v-model="nomContacte" placeholder="Nom contacte">
  <input type="text" v-model="telefonContacte" placeholder="Numero de telefon">
  <button @click="afegirContacte">Afegir contacte</button>
  <input type="text" v-model="filtre" placeholder="Buscar">
  <ul>
  <FillContactes v-for="contacte in filtreResult" :key="contacte.id" :contacte="contacte"/>
  </ul>


  </main>
</template>

<style scoped>
</style>
