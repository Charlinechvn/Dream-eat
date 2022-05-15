
<script setup>

defineProps({
  title: String,
  recipes: Array,
  onClick: Function,
});


</script>

<template>
  <div>
    <details open>
      <summary>{{ title }}</summary>
      <div class="list-choice">
        <div v-for="item in recipes" class="image-container" :key="item.name" @click="onClick(item)">
          <img :src="`src/${item.image}`" />
        </div>
      </div>
    </details>
  </div>
</template>

<style scoped>
h1 {
  font-size: 32px;
  background: linear-gradient(to right, #42d392, #50a2ff);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 15px;
}

.image-container {
  box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.2);
  cursor: pointer;
  width: 150px;
  height: 150px;
  transition: all 0.3s ease;
}
.image-container:hover {
  transform: scale(1.025);
}
.image-container:active {
  transform: scale(0.975);
}

.list-choice {
  padding: 1rem;
  display: flex;
  gap: 1.2rem;
}

summary {
  font-weight: bold;
  font-size: 1em;
  color: #42d392;
  cursor: pointer;
}
</style>
