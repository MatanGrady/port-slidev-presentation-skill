<script setup>
defineProps({
  center: { type: Boolean, default: false },
  spacing: { type: String, default: 'default' } // 'default', 'small', 'none'
})
</script>

<template>
  <div class="impact-box" :class="[{ 'text-center': center }, `spacing-${spacing}`]">
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

.impact-box.spacing-default {
  margin-top: 2rem;
}

.impact-box.spacing-small {
  margin-top: 1rem;
}

.impact-box.spacing-none {
  margin-top: 0;
}
</style>
