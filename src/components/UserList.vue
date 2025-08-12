<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const users = ref([])
let timerId = null

// Fetch data on mount
onMounted(async () => {
  console.log('Component is mounted')

  try {
    const res = await fetch('https://jsonplaceholder.typicode.com/users')
    users.value = await res.json()
  } catch (err) {
    console.error('Error fetching users:', err)
  }

  // Start timer
  timerId = setInterval(() => {
    console.log('Current time:', new Date().toLocaleTimeString())
  }, 1000)
})

// Clean up timer on unmount
onUnmounted(() => {
  console.log('Component is unmounted')
  if (timerId) clearInterval(timerId)
})
</script>

<template>
  <div>
    <h2>User List</h2>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.name }} — {{ user.email }}
      </li>
    </ul>
  </div>
</template>
