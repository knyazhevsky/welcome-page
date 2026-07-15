<template>
  <svg
    :aria-hidden="label ? undefined : 'true'"
    :aria-label="label"
    class="app-icon"
    fill="none"
    focusable="false"
    :height="size"
    :role="label ? 'img' : undefined"
    stroke="currentColor"
    stroke-linecap="round"
    stroke-linejoin="round"
    stroke-width="2"
    viewBox="0 0 24 24"
    :width="size"
  >
    <use :href="`/icons.svg#${name}`" />
  </svg>
</template>

<script setup lang="ts">
export type AppIconName = 'monitor-cog' | 'container' | 'server' | 'bot' | 'arrow-right'

withDefaults(
  defineProps<{
    name: AppIconName
    size?: number | string
    label?: string
  }>(),
  {
    size: 24,
    label: undefined,
  }
)
</script>

<style lang="scss" scoped>
.app-icon {
  display: inline-block;
  flex-shrink: 0;
}
</style>
