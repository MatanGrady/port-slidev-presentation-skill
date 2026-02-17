<script setup lang="ts">
defineProps<{
  src: string
  alt?: string
  rounded?: boolean
  size?: 'small' | 'medium' | 'large' | 'full'
  center?: boolean
}>()
</script>

<template>
  <div v-if="center" class="image-wrapper">
    <img
      :src="src"
      :alt="alt || ''"
      :class="[
        'image',
        rounded !== false && 'rounded',
        size || 'full'
      ]"
    />
  </div>
  <img
    v-else
    :src="src"
    :alt="alt || ''"
    :class="[
      'image',
      rounded !== false && 'rounded',
      size || 'full'
    ]"
  />
</template>

<style scoped>
.image-wrapper {
  display: flex;
  justify-content: center;
}

.image {
  display: block;
}

.image.rounded {
  border-radius: 0.5rem;
}

.image.small {
  max-height: 10rem;
}

.image.medium {
  max-height: 16rem;
}

.image.large {
  max-height: 24rem;
}

.image.full {
  width: 100%;
  height: auto;
}
</style>
