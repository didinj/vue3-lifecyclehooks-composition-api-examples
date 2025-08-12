<script setup>
import { ref, onBeforeUpdate, onUpdated } from 'vue'

const count = ref(0)

function increment() {
  count.value++
}

onBeforeUpdate(() => {
  console.log('DOM will update soon. Current count:', count.value)
})

onUpdated(() => {
  console.log('DOM updated. New count:', count.value)
})
</script>

<template>
  <div>
    <h2>Counter</h2>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
  </div>
</template>
