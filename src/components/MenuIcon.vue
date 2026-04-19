<script setup lang="ts">
defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
})
</script>

<template>
  <span class="menu-icon" :class="{ open: isOpen }" aria-hidden="true">
    <span></span>
    <span></span>
    <span></span>
  </span>
</template>

<script setup>
defineProps({
  isOpen: {
    type: Boolean,
    default: false,
  },
})
</script>

<style scoped>
.menu-icon {
  position: relative;
  width: 20px;
  height: 16px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}

.menu-icon span {
  position: absolute;
  width: 20px;
  height: 2px;
  background: currentColor;
  border-radius: 999px;
  transition: transform 0.2s ease, opacity 0.2s ease;
}

.menu-icon span:nth-child(1) {
  transform: translateY(-6px);
}

.menu-icon span:nth-child(2) {
  transform: translateY(0);
}

.menu-icon span:nth-child(3) {
  transform: translateY(6px);
}

.menu-icon.open span:nth-child(1) {
  transform: rotate(45deg);
}

.menu-icon.open span:nth-child(2) {
  opacity: 0;
}

.menu-icon.open span:nth-child(3) {
  transform: rotate(-45deg);
}
</style>