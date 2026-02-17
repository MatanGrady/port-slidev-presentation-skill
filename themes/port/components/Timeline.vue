<script setup>
defineProps({
  quarters: {
    type: Array,
    default: () => ['Q1', 'Q2', 'Q3', 'Q4']
  }
})
</script>

<template>
  <div class="timeline-container">
    <!-- Timeline axis -->
    <div class="timeline-axis"></div>

    <!-- Quarter markers -->
    <div class="timeline-markers">
      <div
        v-for="(quarter, index) in quarters"
        :key="index"
        class="timeline-marker"
        :style="{ left: `${10 + (index * 80 / (quarters.length - 1))}%` }"
      >
        <div class="marker-dot"></div>
        <div class="marker-label">{{ quarter }}</div>
      </div>
    </div>

    <!-- Content slots for items above and below -->
    <div class="timeline-content">
      <slot></slot>
    </div>
  </div>
</template>

<style scoped>
.timeline-container {
  position: relative;
  height: 16rem;
  margin-top: 2rem;
}

.timeline-axis {
  position: absolute;
  left: 5%;
  right: 5%;
  top: 50%;
  height: 2px;
  background: #e5e7eb;
}

.timeline-markers {
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
}

.timeline-marker {
  position: absolute;
  transform: translateX(-50%);
}

.marker-dot {
  width: 0.5rem;
  height: 0.5rem;
  background: #d1d5db;
  border-radius: 50%;
  transform: translateY(-50%);
}

.marker-label {
  font-size: 0.75rem;
  color: #6b7280;
  margin-top: 0.75rem;
  white-space: nowrap;
}

.timeline-content {
  position: absolute;
  inset: 0;
}
</style>
