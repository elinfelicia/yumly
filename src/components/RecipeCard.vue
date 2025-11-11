<script setup>
    defineProps({
        recipe: {
            type: Object,
            required: true
        }
    })
</script>

<template>
    <div class="recipe-card">
        <h2>{{ recipe.name }}</h2>
        <p>{{ recipe.description }}</p>
    </div>
</template>

<style scoped>
.recipe-card {
  background-color: #ffffff;
  padding: 1.5rem;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease-in-out;
}
.recipe-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}
</style>