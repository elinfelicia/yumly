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
        <div class="recipe-image">
            <img :src="recipe.image" :alt="recipe.name"/>
        </div>
        <div class="recipe-content">
            <h2>{{ recipe.name }}</h2>
            <div class="recipe-details">
                <span>⏱️ {{ recipe.cookingTime }} min</span>
                <span> {{ recipe.ingredientsCount }} ingredients</span>
                <span>⭐ {{ recipe.rating }}</span>
            </div>
            <p class="recipe-description">{{ recipe.description }}</p>
        </div>
    </div>
</template>

<style scoped>
.recipe-card {
  background-color: #ffffff;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  transition: transform 0.2s ease-in-out;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.recipe-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.15);
}

.recipe-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
}

.recipe-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

.recipe-content {
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  flex-grow: 1;
}

.recipe-content h2 {
  margin: 0 0 0.75rem 0;
  color: #2c3e50;
  font-size: 1.25rem;
}

.recipe-details {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
  margin-bottom: 0.75rem;
  flex-wrap: wrap;
  font-size: 0.9rem;
  color: #666;
}

.recipe-description {
  color: #555;
  line-height: 1.6;
  margin: 0;
  font-size: 0.95rem;
  flex-grow: 1;
}
</style>