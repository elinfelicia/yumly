<script setup>
import { RouterView } from 'vue-router'
import Header from '@/components/Header.vue'
</script>

<template>
  <div id="app">
    <Header />
    <RouterView />
  </div>
</template>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: Roboto, sans-serif;
  background-color: #f5f5f5;
  color: #2c3e50;
}

#app {
  min-height: 100vh;
}
</style>
