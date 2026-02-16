<script setup>
defineProps({
  n: { type: [String, Number], required: true }
})
</script>

<template>
  <div class="step-number">{{ n }}</div>
</template>

<style scoped>
.step-number {
  width: 3rem;
  height: 3rem;
  border-radius: 50%;
  background: linear-gradient(135deg, #3b82f6, #8b5cf6);
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 1.25rem;
}
</style>
