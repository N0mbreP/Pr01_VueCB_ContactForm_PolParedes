<script setup>
const props=defineProps({
    contacte:Object,
})

</script>

<template>
      <li>{{ contacte.nom }}  -  {{ contacte.telefon }} </li>
</template>