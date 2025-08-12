<script setup>
import { onMounted } from 'vue'

onMounted(() => {
  // Simulate an error during mount
  throw new Error('Something went wrong in ErrorChild!')
})
</script>

<template>
  <div>
    <p>This content will not render due to the error.</p>
  </div>
</template>