
<script setup>
defineProps({
  title: String
})
</script>

<template>
  <h1>{{ title }}</h1>
</template>

<style scoped>
h1 {
  font-size: 32px;
  background: linear-gradient(to right, #42D392, #50A2FF );
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  }

</style>
