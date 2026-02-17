<script setup>
defineProps({
  n: { type: [String, Number], required: true },
  title: { type: String, required: true }
})
</script>

<template>
  <div class="step-item">
    <div class="step-number">{{ n }}</div>
    <h3 class="step-title">{{ title }}</h3>
    <p class="step-desc"><slot /></p>
  </div>
</template>

<style scoped>
.step-item {
  text-align: center;
  display: grid;
  grid-template-rows: subgrid;
  grid-row: span 3;
  gap: 0.75rem;
  max-width: 300px;
  margin: 0 2rem auto;
}

.step-number {
  width: 3.5rem;
  height: 3.5rem;
  border-radius: 50%;
  background: linear-gradient(135deg, #3b82f6, #8b5cf6);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 1.5rem;
  margin: 0 auto;
  align-self: end;
}

.step-title {
  font-weight: 700;
  font-size: 1.5rem;
  color: #000;
  margin: 0;
  align-self: start;
}

.step-desc {
  color: #6b7280;
  font-size: 1rem;
  line-height: 1.5;
  margin: 0;
  align-self: start;
}

/* Dark mode */
.dark .step-title {
  color: #f9fafb;
}

.dark .step-desc {
  color: #d1d5db;
}
</style>
