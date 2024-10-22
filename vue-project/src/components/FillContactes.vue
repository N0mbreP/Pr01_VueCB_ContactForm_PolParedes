<script setup>
const props=defineProps({
    llistaContactesFill: Array
})
</script>

<template>
    <ul>
      <li v-for="contacte in llistaContactesFill">{{ contacte.nom }}  -  {{ contacte.telefon }} </li>
    </ul>
</template>