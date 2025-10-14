<script setup lang="ts">
  import { computed } from 'vue'

  interface ButtonProps {
    variant: keyof typeof buttonVariants
    size: keyof typeof buttonSizes
    href: string
  }

  const props = defineProps<ButtonProps>()

  const buttonVariants = {
    primary: 'bg-indigo-500 text-neutral-50 border border-indigo-500 hover:bg-indigo-600',
    outline: 'bg-indigo-500/20 text-indigo-500 border border-indigo-500/25 hover:bg-indigo-500/35'
  } as const

  const buttonSizes = {
    md: 'py-2.5 px-6 rounded-full',
    lg: 'py-3.5 px-6 rounded-full'
  } as const

  const buttonClass = computed(() => {
    return `${buttonVariants[props.variant]} ${buttonSizes[props.size]}`
  })
</script>

<template>
  <a 
    class="flex items-center text-base font-medium transition duration-200 active:scale-[0.95]"
    :class="buttonClass"
    :href="props.href"
    target="_blank"
    rel="noopener noreferrer"
  >
    <slot/>
  </a>
</template>