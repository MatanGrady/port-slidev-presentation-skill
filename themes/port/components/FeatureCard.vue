<script setup>
defineProps({
  icon: { type: String, default: '✨' },
  title: { type: String, required: true },
  color: { type: String, default: 'blue' },
  variant: { type: String, default: 'default' }, // 'default' or 'pillar'
  size: { type: String, default: 'default' } // 'default' or 'compact'
})
</script>

<template>
  <div class="feature-card" :class="[`feature-${color}`, variant === 'pillar' && 'pillar', size === 'compact' && 'compact']">
    <div class="feature-content" :class="variant === 'pillar' && 'pillar-content'">
      <div class="feature-icon" :class="variant === 'pillar' && `icon-${color}`">{{ icon }}</div>
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
  min-height: 160px;
}

.feature-card.compact {
  padding: 0.75rem 1rem;
  min-height: auto;
  flex-direction: row;
  align-items: center;
  gap: 0.75rem;
}

.compact .feature-icon {
  font-size: 1.5rem;
  margin-bottom: 0;
}

.compact .feature-title {
  font-size: 1rem;
  margin-bottom: 0;
}

.compact .feature-desc {
  font-size: 0.8rem;
}

.feature-card.pillar {
  background: white;
  box-shadow: 0 1px 3px rgba(0, 0, 0, 0.1);
  text-align: center;
  padding: 1.25rem;
  min-height: 140px;
}

.feature-content {
  flex: 1;
}

.pillar-content {
  display: flex;
  flex-direction: column;
  align-items: center;
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

/* Pillar variant: icon with colored circle background */
.pillar .feature-icon {
  width: 2.5rem;
  height: 2.5rem;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.125rem;
  margin-bottom: 0.75rem;
}

.pillar .icon-blue { background: #dbeafe; }
.pillar .icon-pink { background: #fce7f3; }
.pillar .icon-green { background: #dcfce7; }
.pillar .icon-purple { background: #f3e8ff; }
.pillar .icon-yellow { background: #fef3c7; }
.pillar .icon-orange { background: #ffedd5; }

.feature-title {
  font-size: 1.125rem;
  font-weight: 700;
  color: #1f2937;
  margin-bottom: 0.25rem;
}

.pillar .feature-title {
  font-size: 1.125rem;
  margin-bottom: 0.375rem;
}

.feature-desc {
  font-size: 0.875rem;
  color: #4b5563;
}

.pillar .feature-desc {
  color: #6b7280;
}
</style>
