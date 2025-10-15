<script setup lang="ts">
  import { LINKS } from '@/constants/links'
  import { 
    Linkedin, 
    Github, 
    Mail 
  } from 'lucide-vue-next';
  import avatarImage from '@/assets/images/avatar.png'
  import BaseButton from '../shared/BaseButton.vue'

  const socialsLinks = [
    { 
      icon: Linkedin, 
      label: 'LinkedIn', 
      href: LINKS.LINKEDIN_URL
    },
    { 
      icon: Github, 
      label: 'GitHub', 
      href: LINKS.GITHUB_URL
    },
    { 
      icon: Mail, 
      label: 'Gmail', 
      href: LINKS.GMAIL_URL
    }
  ]
</script>

<template>
  <section class="flex justify-center items-center h-screen">
    <div class="max-w-[1350px] mx-auto px-4">
      <div class="grid grid-cols-2 gap-6">
        <div class="flex flex-col space-y-5">
          <div class="space-y-2.5">
            <h2 class="text-neutral-900 text-5xl font-medium">
              Vamos trabalhar juntos
            </h2>

            <p class="text-neutral-500 text-lg font-normal max-w-[570px]">
              Gostou do meu trabalho? Então entre em contato para que possamos trabalhar juntos
            </p>
          </div>

          <div class="flex items-center space-x-3.5">
            <figure class="size-20">
              <img 
                class="border-2 border-neutral-200 size-full rounded-full"
                :src="avatarImage" 
                alt="Arthur Soares"
              />
            </figure>

            <div class="flex flex-col space-y-1">
              <span class="text-neutral-500 text-base font-normal">
                Arthur Soares
              </span>

              <span class="text-neutral-900 text-lg font-medium">
                Desenvolvedor 
                <span class="bg-gradient-to-r from-indigo-500 to-cyan-500 bg-clip-text text-transparent">
                  Front-end
                </span>
              </span>
            </div>
          </div>

          <div class="flex items-center space-x-2.5"> 
            <BaseButton
              v-for="(value, index) in socialsLinks"
              :key="index"
              variant="outline"
              size="md"
              :href="value.href"
            >
              <component 
                class="size-5 mr-1.5"
                :is="value.icon"
              />

              {{ value.label }}
            </BaseButton>
          </div>
        </div>

        <div class="flex flex-col justify-center items-center border border-neutral-200 p-5 space-y-3.5 rounded-2xl">
          <div class="text-center space-y-1.5">
            <h3 class="text-neutral-900 text-3xl font-medium">
              Pronto para começar?
            </h3>

            <p class="text-neutral-500 text-base font-normal max-w-[390px]">
              Clique no botão abaixo e vamos conversar sobre seu próximo projeto
            </p>
          </div>

          <BaseButton
            variant="primary"
            size="lg"
            :href="LINKS.WHATSAPP_URL"
          >
            Falar no WhatsApp
          </BaseButton>
        </div>
      </div>
    </div>
  </section>
</template>