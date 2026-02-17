<script setup lang="ts">
</script>

<template>
  <p class="note"><slot /></p>
</template>

<style scoped>
.note {
  font-size: 0.875rem;
  color: #6b7280;
  font-style: italic;
  margin-top: 1rem;
}

.dark .note {
  color: #d1d5db;
}
</style>
