<script setup>
// Decorative colored dots for cover slides
</script>

<template>
  <div class="color-dots">
    <span class="dot dot-blue"></span>
    <span class="dot dot-purple"></span>
    <span class="dot dot-pink"></span>
    <span class="dot dot-orange"></span>
    <span class="dot dot-green"></span>
  </div>
</template>

<style scoped>
.color-dots {
  position: absolute;
  bottom: 1.5rem;
  right: 2rem;
  display: flex;
  gap: 0.375rem;
}

.dot {
  width: 0.625rem;
  height: 0.625rem;
  border-radius: 50%;
}

.dot-blue { background: #60a5fa; }
.dot-purple { background: #a78bfa; }
.dot-pink { background: #f472b6; }
.dot-orange { background: #fb923c; }
.dot-green { background: #4ade80; }
</style>
