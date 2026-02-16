<template>
  <div class="slidev-layout cover h-full flex flex-col justify-center px-12">
    <slot />
  </div>
</template>

<style>
:root {
  --port-bg: #f8f9fa;
}

.slidev-layout {
  background: var(--port-bg);
}

.slidev-layout h1 {
  font-weight: 700;
  font-size: 2.5rem;
  color: #000;
  margin-bottom: 2.5rem;
}

.slidev-layout.cover h1 {
  font-size: 3.5rem;
}
</style>
