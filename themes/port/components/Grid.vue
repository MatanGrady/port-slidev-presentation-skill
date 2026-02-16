<script setup>
import { computed } from 'vue'

const props = defineProps({
  cols: { type: [String, Number], default: 2 },
  gap: { type: [String, Number], default: 6 }
})

const gridStyle = computed(() => ({
  display: 'grid',
  gridTemplateColumns: `repeat(${props.cols}, minmax(0, 1fr))`,
  gap: `${props.gap * 0.25}rem`,
  marginTop: '1rem'
}))
</script>

<template>
  <div :style="gridStyle">
    <slot />
  </div>
</template>
