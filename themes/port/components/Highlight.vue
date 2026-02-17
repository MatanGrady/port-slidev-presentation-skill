<script setup lang="ts">
defineProps<{
  weight?: 'light' | 'normal' | 'bold'
}>()
</script>

<template>
  <div :class="['highlight', weight || 'normal']">
    <slot />
  </div>
</template>

<style scoped>
.highlight {
  font-size: 1.5rem;
  line-height: 1.4;
  text-align: center;
  color: #1f2937;
  margin-top: 2rem;
  margin-bottom: 2rem;
}

.highlight.light {
  font-weight: 400;
}

.highlight.normal {
  font-weight: 500;
}

.highlight.bold {
  font-weight: 600;
}
</style>
