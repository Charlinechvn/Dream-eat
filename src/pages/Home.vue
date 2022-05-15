<script setup>
import { fakeRecipes } from "./../data/recipes.fake";

import LinearTitle from "./../components/LinearTitle.vue";
import NavBar from "./../components/NavBar.vue";
import RecipeSelector from "./../components/RecipeSelector.vue";
import RecipeViewer from "./../components/RecipeViewer.vue";
import { ref } from "vue";
import { reactive } from "vue";
const state = reactive({ selectedRecipe: fakeRecipes[0] });

const entrances = ref(
  fakeRecipes.filter((recipe) => recipe.category === "Entrée")
);
const meals = ref(fakeRecipes.filter((recipe) => recipe.category === "Plat"));
const deserts = ref(
  fakeRecipes.filter((recipe) => recipe.category === "Dessert")
);
function _selectRecipe(recipe) {
  state.selectedRecipe = recipe;
}
</script>

<template>
  <main>
    <h1>Recettes italiennes</h1>
    <div class="menu-panel">
      <div class="menu">
        <RecipeSelector
          :onClick="_selectRecipe"
          :recipes="entrances"
          title="Entrée"
        />
        <RecipeSelector
          :onClick="_selectRecipe"
          :recipes="meals"
          title="Plats"
        />
        <RecipeSelector
          :onClick="_selectRecipe"
          :recipes="deserts"
          title="Desserts"
        />
      </div>
      <div class="recipe-selected">
        <RecipeViewer :recipe="state.selectedRecipe" />
      </div>
    </div>
  </main>
</template>

<style>
.menu-panel {
  display: flex;
  justify-content: space-between;
}
.menu {
  flex: 2;
}
.recipe-selected {
  background: inherit;
  box-shadow: 0px 5px 24px 0px rgba(0, 0, 0, 0.15);
  border-radius: 25px;
  flex: 4;
  padding: 1rem 1.5rem;
}
</style>
