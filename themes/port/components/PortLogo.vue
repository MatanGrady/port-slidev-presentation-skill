<script setup lang="ts">
defineProps<{
  type?: 'svg' | 'png'
  color?: 'black' | 'white'
  size?: string
}>()
</script>

<template>
  <img
    v-if="type === 'png'"
    :src="`/port-symbol-${color || 'black'}.png`"
    :class="size ? '' : 'h-8'"
    :style="size ? { height: size } : {}"
    alt="Port"
  />
  <svg
    v-else
    :class="size ? '' : 'h-8 w-8'"
    :style="size ? { height: size, width: size } : {}"
    viewBox="0 0 400 400"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path
      fill-rule="evenodd"
      clip-rule="evenodd"
      d="M75 231.238L200.562 231.239L75 105.683V231.238ZM75 274.716V275C75 302.614 97.3858 325 125 325H325V125C325 97.3858 302.614 75 275 75H274.727L274.726 274.715H274.282V274.717L75 274.716ZM229.89 75L229.89 199.079L105.805 75H229.89Z"
      :fill="color || 'black'"
    />
  </svg>
</template>
