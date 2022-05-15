<script setup>
import { ref, reactive } from "vue";
import Button from './../../components/Button.vue'
import LinearTitle from './../../components/LinearTitle.vue'
import Badge from './../../components/Badge.vue'

const state = reactive({
    name: 'Votre titre de recette', 
    type: 'Entrée',
    image: '',
    prepTime: 5,
    ingredients: {},
    steps: [],
})

const storeRecipe = () => {
  console.log("name =>" + state.name)
  console.log("type =>" + state.type)
  console.log("image =>" + state.image)
  console.log("prepTime =>" + state.prepTime)
  console.log("ingredients =>" + state.ingredients)
  console.log("steps =>" + state.steps)


  window.location = '/'
}
</script>

<template>
<main>
    <div class="menu-panel">
      <div class="menu">
        <div>
          <input
            type="text"
            v-model="state.name"
            placeholder="Titre..."
          />
          <select v-model="state.type">
              <option value="Entrée">Entrée</option>
              <option value="Plat">Plat</option>
              <option value="Dessert">Dessert</option>
          </select>
        </div>

        <div>
          <input
            type="number"
            v-model="state.prepTime"
          />
        </div>
      </div>
      <div class="recipe-selected">
        <LinearTitle :title="state.name" />
        <Badge :text="state.prepTime + ' min'" />
        Image: {{ state.image }}<br>
        prepTime: {{ state.prepTime }}<br>
        
        <ul>
          <li v-bind:key="index" v-for="(step, index) in state.steps">
            {{ step }}
          </li>
        </ul>
      </div>
    </div>
    <div class="submit-container">
      <Button @click="storeRecipe" title="Sauvegarder 👨🏻‍🍳" />
    </div>
  </main>
</template>

<style scoped>
.submit-container {
    margin-top: 45px;
    max-width: 200px;
    margin-left: auto;
    margin-right: auto;
}
</style>