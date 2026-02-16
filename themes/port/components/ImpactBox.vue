<script setup>
defineProps({
  center: { type: Boolean, default: false }
})
</script>

<template>
  <div class="impact-box" :class="{ 'text-center': center }">
    <slot />
  </div>
</template>

<style scoped>
.impact-box {
  background: #000;
  color: white;
  padding: 1.5rem;
  border-radius: 16px;
}
</style>
