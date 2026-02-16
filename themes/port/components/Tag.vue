<script setup>
defineProps({
  color: { type: String, default: 'blue' }
})
</script>

<template>
  <span class="tag" :class="`tag-${color}`">
    <slot />
  </span>
</template>

<style scoped>
.tag {
  display: inline-block;
  padding: 0.25rem 0.875rem;
  border-radius: 9999px;
  font-size: 0.875rem;
  font-weight: 500;
}

.tag-blue { background: #dbeafe; color: #1e40af; }
.tag-pink { background: #fce7f3; color: #9d174d; }
.tag-green { background: #dcfce7; color: #166534; }
.tag-yellow { background: #fef3c7; color: #92400e; }
.tag-purple { background: #f3e8ff; color: #6b21a8; }
.tag-orange { background: #ffedd5; color: #c2410c; }
.tag-dark { background: #000; color: white; }
</style>
