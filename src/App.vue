<script setup>

import Random from './components/Random.vue'
import { onMounted, ref } from 'vue'

const fact = ref('')

const getFact = async () => {
  const response = await fetch('https://uselessfacts.jsph.pl/random.json?language=en')
  const data = await response.json()
  fact.value = data.text
}

onMounted(() => {
  getFact()
})

</script>

<template>
  <main>
    <h3>Here's your Random Fact of the Day</h3>
    {{ fact }}
  </main>
</template>

<style scoped>

</style>
