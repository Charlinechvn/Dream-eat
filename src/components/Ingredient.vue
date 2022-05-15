
<script setup>
defineProps({
  name: String,
  image: String,
  quantity: String,
});
</script>

<template>
  <div class="container">
    <img :src="`src/${image}`" width="44" />
    <div class="details">
      <span>{{ name }}</span>
      <span>{{ quantity }}</span>
    </div>
  </div>
</template>

<style scoped>
.container {
  padding: 0.5rem 1rem;
  color: #F2F2F2;
  border-radius: 15px;
  border: 1px solid #50A2FF;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 75px;
  font-size: 0.75rem;
  font-weight: bold;
  gap: 0.5rem;
}

.details{
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>
