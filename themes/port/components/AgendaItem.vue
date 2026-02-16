<script setup>
defineProps({
  icon: { type: String, default: '📌' },
  color: { type: String, default: 'blue' }
})
</script>

<template>
  <div class="agenda-item" :class="`agenda-${color}`">
    <span class="agenda-icon">{{ icon }}</span>
    <span class="agenda-text"><slot /></span>
  </div>
</template>

<style scoped>
.agenda-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  border-radius: 16px;
  padding: 1.25rem 1.5rem;
}

.agenda-icon {
  font-size: 1.5rem;
}

.agenda-text {
  font-weight: 600;
  color: #1f2937;
}

.agenda-blue { background: #dbeafe; }
.agenda-pink { background: #fce7f3; }
.agenda-green { background: #dcfce7; }
.agenda-purple { background: #f3e8ff; }
.agenda-yellow { background: #fef3c7; }
.agenda-orange { background: #ffedd5; }
</style>
