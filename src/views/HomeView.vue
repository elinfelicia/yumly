<script setup>
    import { ref, computed } from 'vue'
    import { recipes } from '../data/mockRecipes.js'
    import RecipeCard from '../components/RecipeCard.vue'
    import Searchbar from '../components/SearchBar.vue'
    import CategoryList from '../components/CategoryList.vue'

    const searchQuery = ref('');
    const filteredRecipes = computed (() => {
      const query = searchQuery.value.trim().toLowerCase()

      if (!query) {
        return recipes;
      }
      return recipes.filter(recipe => {
        return (
          recipe.name.toLowerCase().includes(query) ||
          recipe.description.toLowerCase().includes(query) ||
          recipe.ingredients.some(ingredient => ingredient.toLowerCase().includes(query)) ||
          recipe.steps.some(step => step.toLowerCase().includes(query))
        );
      });
    });
    
</script>

<template>
  <div class="home-view">
    <h1>Yumly - Recipe Collection</h1>
    <Searchbar v-model="searchQuery" />
    <div class="main-content">
      <div class="recipes-list">
        <RecipeCard v-for="recipe in filteredRecipes" :key="recipe.id" :recipe="recipe" />
      </div>
      <CategoryList />
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

.main-content {
  display: flex;
  gap: 2rem;
  margin-top: 2rem;
  align-items: flex-start;
}

.recipes-list {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 1rem;
  flex: 1;
}

</style>

