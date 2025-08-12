<script setup>
import { ref } from 'vue'
import Profile from './components/Profile.vue'
import Settings from './components/Settings.vue'

const currentTab = ref('Profile')
const tabs = { Profile, Settings }
</script>

<template>
  <div>
    <h1>Keep-Alive Example</h1>
    <button @click="currentTab = 'Profile'">Profile</button>
    <button @click="currentTab = 'Settings'">Settings</button>

    <!-- Cache the components -->
    <keep-alive>
      <component :is="tabs[currentTab]" />
    </keep-alive>
  </div>
</template>

