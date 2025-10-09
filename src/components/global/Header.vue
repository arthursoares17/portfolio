<script setup lang="ts">
  import type { Component } from 'vue'

  interface SectionItem {
    id: string
    icon: Component
    label: string
    component: Component
  }

  const props = defineProps<{
    items: SectionItem[]
    current: string | undefined
  }>()

  const emit = defineEmits<{
    (e: 'update:current', value: string):void
  }>()

  const handleSection = (value: string) => {
    emit('update:current', value)
  }
</script>

<template>
  <header class="fixed left-0 right-0 bottom-6 z-20">
    <div class="max-w-[490px] mx-auto px-4">
      <nav class="flex items-center bg-neutral-50 border-2 border-neutral-300 p-2 space-x-2.5 rounded-full">
        <button
          class="cursor-pointer flex items-center space-x-1.5 group"
          v-for="value in props.items"
          :key="value.id"
          :class="[
            props.current === value.id
            ? 'bg-indigo-500 text-neutral-50 py-2 px-3 rounded-full'
            : 'text-neutral-500 py-2 px-3 transition-all duration-200 rounded-full hover:bg-neutral-300 hover:text-neutral-900 active:scale-[0.95]'
          ]"
          @click="handleSection(value.id)"
        >
          <component 
            class="size-5 transition duration-400"
            :is="value.icon"
            :class="[
              props.current === value.id
              ? 'group-hover:rotate-0'
              : 'group-hover:rotate-12'
            ]"
          />

          <span class="text-base font-medium">
            {{ value.label }}
          </span>
        </button>
      </nav>
    </div>
  </header>
</template>