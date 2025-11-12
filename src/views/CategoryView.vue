<script setup>
import { computed, onMounted } from 'vue';
import { useRoute } from 'vue-router';
import { getRecipesByCategory, getCategoryBySlug } from '../data/mockRecipes.js';
import RecipeCard from '../components/RecipeCard.vue';
import CategoryList from '../components/CategoryList.vue';

const route = useRoute();
const categorySlug = computed(() => route.params.categorySlug);
const category = computed(() => getCategoryBySlug(categorySlug.value));
const recipes = computed(() => getRecipesByCategory(categorySlug.value));

</script>

<template>
    <div class="category-view">
        <div v-if="!category" class="error-message">
            <h2>Category not found</h2>
            <p>Sorry, this category doesn't exist.</p>
        </div>
        <div v-else>
            <h1>{{ category.name }} Recipes</h1>
            <p class="recipe-count">{{ recipes.length }} recipe{{ recipes.length !== 1 ? 's' : '' }} found</p>
            <div class="main-content">
                <div v-if="recipes.length === 0" class="no-recipes">
                    No recipes in this category yet.
                </div>
                <div v-else class="recipes-list">
                    <RecipeCard v-for="recipe in recipes" :key="recipe.id" :recipe="recipe" />
                </div>
                <CategoryList />
            </div>
        </div>
    </div>
</template>

<style scoped>
.category-view {
    padding: 2rem;
    margin: 0 auto;
}

h1 {
    margin-bottom: 0.5rem;
    color: #2c3e50;
}

.recipe-count {
    color: #666;
    margin-bottom: 2rem;
}

.main-content {
    display: flex;
    gap: 2rem;
    align-items: flex-start;
}

.recipes-list {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1rem;
    flex: 1;
}

.error-message,
.no-recipes {
    text-align: center;
    padding: 3rem;
    color: #999;
    flex: 1;
}

.error-message h2 {
    color: #2c3e50;
    margin-bottom: 0.5rem;
}
</style>