<script setup>
defineProps({
  icon: { type: String, default: '✨' },
  title: { type: String, required: true },
  color: { type: String, default: 'blue' }
})
</script>

<template>
  <div class="feature-card" :class="`feature-${color}`">
    <div class="feature-content">
      <div class="feature-icon">{{ icon }}</div>
      <h3 class="feature-title">{{ title }}</h3>
      <p class="feature-desc"><slot /></p>
    </div>
    <div v-if="$slots.tags" class="feature-tags">
      <slot name="tags" />
    </div>
  </div>
</template>

<style scoped>
.feature-card {
  border-radius: 16px;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  min-height: 180px;
}

.feature-content {
  flex: 1;
}

.feature-tags {
  margin-top: auto;
  padding-top: 0.5rem;
  display: flex;
  flex-wrap: wrap;
  gap: 0.375rem;
}

.feature-blue { background: #dbeafe; }
.feature-pink { background: #fce7f3; }
.feature-green { background: #dcfce7; }
.feature-purple { background: #f3e8ff; }
.feature-yellow { background: #fef3c7; }
.feature-orange { background: #ffedd5; }

.feature-icon {
  font-size: 2rem;
  margin-bottom: 0.5rem;
}

.feature-title {
  font-size: 1.125rem;
  font-weight: 700;
  color: #1f2937;
  margin-bottom: 0.25rem;
}

.feature-desc {
  font-size: 0.875rem;
  color: #4b5563;
}
</style>
