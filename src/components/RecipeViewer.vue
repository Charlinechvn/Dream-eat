
<script setup>
import Ingredient from "./../components/Ingredient.vue";
import LinearTitle from "./../components/LinearTitle.vue";
import Badge from "./../components/Badge.vue";
import Step from "./../components/Step.vue";

defineProps({
  recipe: Object,
});
</script>

<template>
  <div class="container">
    <div class="header">
      <LinearTitle :title="recipe?.name" />
      <Badge :text="`${recipe?.prepTime} min`" />
    </div>
    <div class="visual">
      <img :src="`src/${recipe?.image}`" width="250" height="250" />
      <div class="ingredient-list">
      <Ingredient v-for="ingredient in recipe?.ingredients" :key="ingredient.name" :name="ingredient.name" :quantity="ingredient.quantity"  :image="ingredient.image" />
      </div>
    </div>
    <div class="steps">
      <Step v-for="step in recipe?.steps" :key="step" :step="step" />
  </div>
  </div>
</template>

<style scoped>
img{
  border-radius: 15px;
}
.visual{
  display: flex;
  gap: 1rem;
}
.header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.ingredient-list{
  display: flex;
  flex-wrap: wrap;
  align-items: flex-start;
  gap: 1rem;
}
</style>
