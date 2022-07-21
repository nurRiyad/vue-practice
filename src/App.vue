<script setup lang="ts">
import { ref } from "vue";

const isActive = ref(3);
</script>

<template>
  <div class="container">
    <img
      :class="{ active: isActive === 1 }"
      @click="isActive = 1"
      src="./images/111.webp"
      alt="img1"
    />
    <img
      :class="{ active: isActive === 2 }"
      @click="isActive = 2"
      src="./images/222.webp"
      alt="img3"
    />
    <img
      :class="{ active: isActive === 3 }"
      @click="isActive = 3"
      src="./images/333.webp"
      alt="img1"
    />
    <img
      :class="{ active: isActive === 4 }"
      @click="isActive = 4"
      src="./images/444.webp"
      alt="img4"
    />
    <img
      :class="{ active: isActive === 5 }"
      @click="isActive = 5"
      src="./images/555.webp"
      alt="img5"
    />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  width: 90vw;
}
img {
  height: 90vh;
  width: 80px;
  object-fit: cover;
  border-radius: 20px;
  padding: 4px;
  cursor: pointer;
  transition: flex 0.7s ease-out;
}

.active {
  flex-grow: 10;
}

@media (max-width: 480px) {
  .container {
    display: flex;
    flex-direction: column;
  }
  img {
    height: 50px;
    width: 90vw;
    transition: height 0.7s ease-out;
  }
  .active {
    height: 500px;
  }
}
</style>
