<template>
  <div class="slidev-layout section h-full flex items-center justify-center px-12">
    <div class="flex items-center gap-12">
      <div class="section-number">{{ $slidev.configs.number || '01' }}</div>
      <div class="section-content">
        <slot />
      </div>
    </div>
  </div>
</template>

<style>
.slidev-layout.section h1 {
  font-weight: 700;
  font-size: 2.5rem;
  color: #000;
  margin: 0;
  margin-bottom: 0.5rem;
}

.section-number {
  font-size: 6rem;
  font-weight: 800;
  line-height: 1;
  background: linear-gradient(135deg, #3b82f6, #8b5cf6);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-content .subtitle {
  margin-top: 0;
}
</style>
