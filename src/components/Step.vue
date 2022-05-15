
<script setup>
defineProps({
  step: String,
});
</script>

<template>
  <div class="container">
    <h3>Etapes</h3>
    <p>{{step}}</p>
  </div>
</template>

<style scoped>
.container {
}
p{
  margin-left: 2rem;
  color: #f2f2f2;
  display: flex;
  margin-top: 0px;
  padding-top: 0px;
}
h3{
  font-size: 1.5rem;
  font-weight: bold;
  color: #50A2FF;
  margin-bottom: 0px;
  padding-bottom: 0px;
}

</style>
