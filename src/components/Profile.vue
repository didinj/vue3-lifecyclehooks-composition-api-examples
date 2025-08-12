<script setup>
import { ref, onActivated, onDeactivated } from 'vue'

const visits = ref(0)

onActivated(() => {
  visits.value++
  console.log('Profile component activated. Visit count:', visits.value)
})

onDeactivated(() => {
  console.log('Profile component deactivated')
})
</script>

<template>
  <div>
    <h2>Profile Page</h2>
    <p>Visited this tab: {{ visits }} times</p>
  </div>
</template>
