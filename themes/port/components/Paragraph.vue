<script setup lang="ts">
defineProps<{
  center?: boolean
  bold?: boolean
}>()
</script>

<template>
  <p :class="['paragraph', { center, bold }]"><slot /></p>
</template>

<style scoped>
.paragraph {
  font-size: 1.125rem;
  color: #374151;
  margin-top: 1rem;
  margin-bottom: 1rem;
  line-height: 1.6;
}

.paragraph.center {
  text-align: center;
}

.paragraph.bold {
  font-weight: 600;
}
</style>
