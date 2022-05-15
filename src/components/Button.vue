
<script setup>
defineProps({
  title: String
})
</script>

<template>
 <button>{{title}}</button>
</template>

<style scoped>
button {
  background-image: linear-gradient(30deg,#50A2FF, #42D392);
  transition: all .3s ease;
  border: none;
  padding: 0.5em 1em;
  font-size: 1em;
  border-radius: 0.5em;
  font-weight: bold;
  cursor: pointer;
}
button:hover {
  opacity: 0.7;
  transform: scale(1.025);
}
button:active {
  transform: scale(0.975);
}

</style>
