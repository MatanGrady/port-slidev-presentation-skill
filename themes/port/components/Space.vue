<script setup lang="ts">
defineProps<{
  size?: 'small' | 'medium' | 'large'
}>()
</script>

<template>
  <div :class="['space', size || 'medium']"></div>
</template>

<style scoped>
.space.small {
  height: 0.5rem;
}

.space.medium {
  height: 1rem;
}

.space.large {
  height: 2rem;
}
</style>
