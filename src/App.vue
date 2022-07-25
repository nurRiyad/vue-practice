<script setup lang="ts">
import { ref } from "vue";
const activeBar = ref(1);
</script>

<template>
  <div class="container">
    <div class="progress-container">
      <div
        class="progress"
        :style="{ width: (activeBar - 1) * 25 + '%' }"
      ></div>
      <div class="circle" :class="{ active: activeBar >= 1 }">1</div>
      <div class="circle" :class="{ active: activeBar >= 2 }">2</div>
      <div class="circle" :class="{ active: activeBar >= 3 }">3</div>
      <div class="circle" :class="{ active: activeBar >= 4 }">4</div>
      <div class="circle" :class="{ active: activeBar >= 5 }">5</div>
    </div>
    <button class="btn" @click="activeBar -= 1" :disabled="activeBar === 1">
      Prev
    </button>
    <button class="btn" @click="activeBar += 1" :disabled="activeBar === 5">
      Next
    </button>
  </div>
</template>

<style>
.container {
  text-align: center;
}
.progress-container {
  display: flex;
  justify-content: space-between;
  max-width: 100%;
  width: 400px;
  position: relative;
  margin-bottom: 30px;
}

.progress-container::before {
  content: "";
  background-color: var(--line-border-empty);
  position: absolute;
  top: 50%;
  left: 0;
  height: 4px;
  width: 100%;
  transform: translateY(-50%);
  z-index: -1;
}

.progress {
  background-color: var(--line-border-fill);
  position: absolute;
  top: 50%;
  left: 0;
  height: 4px;
  transform: translateY(-50%);
  transition: 0.4s ease;
  z-index: -1;
}

.circle {
  color: #999;
  background-color: #fff;
  border: 3px solid var(--line-border-empty);
  border-radius: 50%;
  height: 40px;
  width: 40px;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: 0.4s ease;
}

.circle.active {
  border-color: var(--line-border-fill);
}

.btn {
  color: #fff;
  background-color: var(--line-border-fill);
  border: 0;
  border-radius: 6px;
  font-size: 15px;
  font-family: inherit;
  padding: 5px 30px;
  margin: 5px;
  cursor: pointer;
}

.btn:active {
  transform: scale(0.97);
}

.btn:focus {
  outline: 0;
}

.btn:disabled {
  background-color: var(--line-border-empty);
  cursor: not-allowed;
}
</style>
