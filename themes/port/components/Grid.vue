<script setup>
import { computed } from 'vue'

const props = defineProps({
  cols: { type: [String, Number], default: 2 },
  gap: { type: [String, Number], default: 6 }
})

const gridStyle = computed(() => ({
  gridTemplateColumns: `repeat(${props.cols}, minmax(0, 1fr))`,
  gap: `${props.gap * 0.25}rem`
}))
</script>

<template>
  <div class="port-grid" :style="gridStyle">
    <slot />
  </div>
</template>

<style scoped>
.port-grid {
  display: grid;
  margin-top: 1.5rem;
}
</style>
