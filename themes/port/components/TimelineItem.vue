<script setup>
defineProps({
  position: {
    type: String,
    default: 'above',
    validator: (v) => ['above', 'below'].includes(v)
  },
  left: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    default: ''
  },
  status: {
    type: String,
    default: ''
  }
})
</script>

<template>
  <div
    class="timeline-item"
    :class="position"
    :style="{ left }"
  >
    <div class="item-pill">
      <span v-if="icon" class="item-icon">{{ icon }}</span>
      <span class="item-text"><slot></slot></span>
      <span v-if="status" class="item-status">{{ status }}</span>
    </div>
  </div>
</template>

<style scoped>
.timeline-item {
  position: absolute;
}

.timeline-item.above {
  bottom: 55%;
}

.timeline-item.below {
  top: 55%;
}

.item-pill {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  background: white;
  border: 1px solid #e5e7eb;
  border-radius: 9999px;
  padding: 0.5rem 1rem;
  font-size: 0.875rem;
  font-weight: 500;
  white-space: nowrap;
  color: #1f2937;
}

.item-icon {
  font-size: 1rem;
}

.item-status {
  background: #f3f4f6;
  color: #374151;
  padding: 0.125rem 0.5rem;
  border-radius: 9999px;
  font-size: 0.75rem;
}

/* Dark mode */
.dark .item-pill {
  background: #1a1a2e;
  border-color: #374151;
  color: #f9fafb;
}

.dark .item-status {
  background: #374151;
  color: #d1d5db;
}
</style>
