<script setup>
import { computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())
</script>

<template>
  <footer class="app-footer">
    <div class="footer-content">
      <p>&copy; {{ currentYear }} Yumly. All rights reserved.</p>
      <p class="tagline">Discover delicious recipes for every occasion</p>
    </div>
  </footer>
</template>

<style scoped>
.app-footer {
  background-color: #647f81;
  color: #fff;
  padding: 2rem;
  margin-top: auto;
}

.footer-content {
  max-width: 1200px;
  margin: 0 auto;
  text-align: center;
}

.footer-content p {
  margin: 0.5rem 0;
}

.tagline {
  font-size: 0.9rem;
  opacity: 0.8;
}
</style>

