<script setup>
import { computed } from 'vue'
import { categories, getRecipeCountByCategory } from '@/data/mockRecipes.js'
import { RouterLink, useRoute } from 'vue-router'

const route = useRoute();

const categoriesWithCount = computed(() => {
  return categories.map(category => {
    return {
      ...category,
      count: getRecipeCountByCategory(category.id)
    }
  })
});

const isActiveCategory = (categorySlug) => {
  return route.params.categorySlug === categorySlug
};
</script>

<template>
    <div class="category-list">
        <h2 class="category-title">Categories</h2>
        <div v-if="categoriesWithCount.length === 0" class="no-categories">
            No categories found
        </div>
        <div v-else class="categories">
            <RouterLink 
                v-for="category in categoriesWithCount" 
                :key="category.id" 
                :to="`/category/${category.slug}`"
                class="category-item"
                :class="{ active: isActiveCategory(category.slug) }"
            >
                <span class="category-name">{{ category.name }}</span>
                <span class="category-count">({{ category.count }})</span>
            </RouterLink>
        </div>
    </div>
</template>

<style scoped>
.category-list {
    background: white;
    padding: 1.5rem;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
    min-width: 250px;
    flex-shrink: 0;
}

.category-title {
    margin: 0 0 1rem 0;
    font-size: 1.25rem;
    color: #2c3e50;
}

.categories {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
}

.category-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0.75rem 1rem;
    text-decoration: none;
    color: #333;
    border-radius: 6px;
    transition: background-color 0.2s, color 0.2s;
    border: 1px solid transparent;
}

.category-item:hover {
    background-color: #f5f5f5;
}

.category-item.active {
    background-color: #647f81;
    color: #fff;
    border-color: #647f81;
}

.category-name {
    font-weight: 500;
}

.category-count {
    font-size: 0.9rem;
    opacity: 0.8;
}
</style>