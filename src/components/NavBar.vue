<script setup>
import Button from "./Button.vue";
import LinearTitle from "./LinearTitle.vue";

const redirectToCreatePage = () => {
  window.location = '/#/create'
}

</script>
<template>
  <nav>
    <ul>
      <li>
        <a href="/">
          <LinearTitle title="Dream Eat" />
        </a>
      </li>
      <li>
        <Button @click="redirectToCreatePage" title="Ajouter une recette 🍚" />
      </li>
    </ul>
  </nav>
</template>

<style scoped>
nav {
  padding-top: 20px;
}
ul {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  justify-content: space-between;
  align-items: center;
}
</style>
