<script setup>
defineProps({
  value: { type: String, required: true },
  label: { type: String, required: true }
})
</script>

<template>
  <div class="metric-card">
    <p class="metric-value">{{ value }}</p>
    <p class="metric-label">{{ label }}</p>
  </div>
</template>

<style scoped>
.metric-card {
  background: white;
  border-radius: 16px;
  padding: 1rem 1.5rem;
  border: 1px solid #e5e7eb;
  box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.05);
  text-align: center;
}

.metric-value {
  font-size: 2.25rem;
  font-weight: 700;
  color: #1f2937;
}

.metric-label {
  color: #6b7280;
  font-size: 0.875rem;
  margin-top: 0.5rem;
}
</style>
