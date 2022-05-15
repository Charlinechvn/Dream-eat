
<script setup>
defineProps({
  text: Number,
});
</script>

<template>
  <div class="container">
    <p>{{ text }}</p>
  </div>
</template>

<style scoped>
.container {
  background: #42D392;
  color: #333;
  border-radius: 15px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: fit-content;
  padding: 0rem 0.75rem;
  font-weight: bold;
}
</style>
