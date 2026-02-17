<script setup lang="ts">
defineProps<{
  title?: string
  subtitle?: string
}>()
</script>

<template>
  <div class="placeholder-wrapper">
    <div class="placeholder-box">
      <p class="placeholder-title">{{ title || 'Content placeholder' }}</p>
      <p v-if="subtitle" class="placeholder-subtitle">{{ subtitle }}</p>
    </div>
  </div>
</template>

<style scoped>
.placeholder-wrapper {
  display: flex;
  justify-content: center;
  margin-top: 4rem;
}

.placeholder-box {
  background: white;
  padding: 3rem;
  border-radius: 0.5rem;
  border: 1px solid #e5e7eb;
  display: inline-block;
  text-align: center;
}

.placeholder-title {
  color: #6b7280;
  font-size: 1.25rem;
}

.placeholder-subtitle {
  color: #9ca3af;
  margin-top: 1rem;
}

/* Dark mode */
.dark .placeholder-box {
  background: #1a1a2e;
  border-color: #374151;
}

.dark .placeholder-title {
  color: #d1d5db;
}

.dark .placeholder-subtitle {
  color: #9ca3af;
}
</style>
