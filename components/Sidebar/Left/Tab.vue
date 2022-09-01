<script setup lang="ts">
import useTailwindConfig from '~/composables/useTailwindConfig'

const props = withDefaults(
  defineProps<{
    active: boolean
  }>(),
  {
    active: false,
  }
)

const textClasses = computed(() =>
  props.active ? 'font-semibold' : 'font-normal'
)

const { defaultTransition } = useTailwindConfig()
</script>

<template>
  <nuxt-link
    to="#"
    class="flex items-center p-3 text-black rounded-full w-min hover:bg-gray-200 dark:hover:bg-dim-200 dark:text-white"
    :class="defaultTransition"
  >
    <div class="w-6 h-6 text-dark">
      <slot name="icon" />
    </div>

    <div
      class="hidden ml-4 text-xl xl:block"
      :class="textClasses"
    >
      <slot name="name" />
    </div>
  </nuxt-link>
</template>

<style scoped></style>
