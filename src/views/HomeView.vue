<script setup>
import HeaderPage from '@/components/HeaderPage.vue'
import data from '@/data/szpej.json'
import { ref } from 'vue'

const equipment = data
const trip = ref([])

trip.value = equipment
  .map(({ name, category }) => ({
    name,
    category: category.some((el) => el === 'skitour')
  }))
  .filter((el) => el.category === true)
</script>

<template>
  <HeaderPage />
  <main>
    <h1>Home Page</h1>
    <div>Iość: {{ trip.length }}</div>
    <div>{{ trip }}</div>
  </main>
</template>
