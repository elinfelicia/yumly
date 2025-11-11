<script setup>
    import { recipes } from '../data/mockRecipes.js'
    import RecipeCard from '../components/RecipeCard.vue'
</script>

<template>
  <div class="home-view">
    <h1>Yumly - Recipe Collection</h1>
    <p>Collecting yummy recipes!</p>
    <div class="recipes-list">
      <RecipeCard v-for="recipe in recipes" :key="recipe.id" :recipe="recipe" />
    </div>
  </div>
</template>


<style scoped>
.home-view {
  padding: 2rem;
  text-align: center;
}

h1 {
  margin-bottom: 1rem;
  color: #2c3e50;
}

.recipes-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
}

</style>

