<script setup>
import { ref, computed } from 'vue'

/**
 * Layout
 */
import NavBar from './components/NavBar.vue'

/**
 * Pages
 * @see ./pages
 */
import Home from './pages/Home.vue'
import CreateRecipePage from './pages/Recipes/Create.vue'
import NotFound from './pages/NotFound.vue'


/**
 * Routing
 * @see https://vuejs.org/guide/scaling-up/routing.html#simple-routing-from-scratch
 */
const routes = {
  '/': Home,
  '/create': CreateRecipePage
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentPage = computed(() => {
  return routes[currentPath.value.slice(1) || '/'] || NotFound
})
</script>

<template>
  <header>
    <NavBar />
  </header>
  <component :is="currentPage" />
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  max-width: 1280px;
  margin: 0 auto;
  height: 100%;
}

h1 {
  color: #EBEBEB;
}

a {
  text-decoration: none;
}
</style>