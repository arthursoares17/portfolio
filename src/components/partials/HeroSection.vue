<script setup lang="ts">
  import { LINKS } from '@/constants/links'
  import { Download } from 'lucide-vue-next'
  import avatarImage from '@/assets/images/avatar-image.png'
  import BaseButton from '../shared/BaseButton.vue'
</script>

<template>
  <section class="flex justify-center items-center h-screen">
    <div class="max-w-[1350px] mx-auto px-4">
      <div class="flex flex-col items-center space-y-3.5">
        <figure class="size-26">
          <img 
            class="border-2 border-neutral-200 size-full rounded-full"
            :src="avatarImage" 
            alt="Arthur Soares"
          />
        </figure>

        <div class="text-center space-y-1.5">
          <h2 class="text-neutral-500 text-xl font-normal">
            Olá, eu sou o Arthur Soares
          </h2>
              
          <h1 class="text-neutral-900 text-6xl font-medium">
            Desenvolvedor 
            <span class="bg-gradient-to-r from-indigo-500 to-cyan-500 bg-clip-text text-transparent">
              Front-end
            </span>
          </h1>
        </div>

        <p class="text-neutral-500 text-xl font-normal text-center max-w-[600px]">
          Transformo ideias em interfaces interativas e experiências digitais que encantam pessoas
        </p>

        <div class="flex items-center space-x-3.5">
          <BaseButton 
            variant="primary" 
            size="lg"
            :href="LINKS.WHATSAPP_URL"
          >
            Entre em contato
          </BaseButton>

          <BaseButton 
            variant="outline" 
            size="lg"
            :href="LINKS.DRIVE_FILE_URL"
          >
            <Download class="size-5 mr-1.5"/>

            Download cv
          </BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>