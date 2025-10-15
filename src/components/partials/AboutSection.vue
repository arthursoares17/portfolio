<script setup lang="ts">
  import { 
    Code, 
    LayoutDashboard, 
    Zap, 
    UsersRound 
  } from 'lucide-vue-next'

  const highlights = [
    {
      icon: Code,
      title: 'Código Limpo',
      description: 'Escrevo código organizado, escalável e fácil de manter.'
    },
    {
      icon: LayoutDashboard,
      title: 'Design Moderno',
      description: 'Interfaces bonitas e funcionais que encantam usuários.'
    },
    {
      icon: Zap,
      title: 'Performance',
      description: 'Aplicações rápidas e otimizadas para melhor experiência.'
    },
    {
      icon: UsersRound,
      title: 'Colaboração',
      description: 'Trabalho em equipe e comunicação eficiente em projetos.'
    }
  ]
</script>

<template>
  <section class="flex justify-center items-center h-screen">
    <div class="max-w-[1350px] mx-auto px-4">
      <div class="grid grid-cols-2 gap-6">
        <div class="space-y-5">
          <h3 class="text-neutral-900 text-5xl font-medium">
            Sobre mim
          </h3>

          <div class="space-y-4">
            <p class="text-neutral-500 text-lg font-normal">
              Meu nome é Arthur Soares, sou Desenvolvedor Front-end especializado em criar interfaces inteligentes, responsivas e centradas na experiência do usuário. Tenho experiência prática com Vue.js e Nuxt.js, desenvolvendo aplicações web modernas que combinam design impecável com performance e funcionalidade.
            </p>

            <p class="text-neutral-500 text-lg font-normal">
              Trabalho com tecnologias atuais do ecossistema JavaScript, entregando soluções bem estruturadas e voltadas para resultados reais. Embora minha expertise seja front-end, tenho interesse genuíno em explorar o back-end para construir uma visão completa do desenvolvimento web. 
            </p>
          </div>
        </div>

        <div class="grid grid-cols-2 gap-4">
          <div
            class="border border-neutral-200 p-5 space-y-3 rounded-2xl"
            v-for="(value, index) in highlights"
            :key="index"
          >
            <div class="flex justify-center items-center bg-indigo-500/20 border border-indigo-500/25 size-10 rounded-lg">
              <component
                class="text-indigo-500 size-5"
                :is="value.icon"
              />
            </div>

            <div class="space-y-1">
              <h4 class="text-neutral-900 text-base font-medium">
                {{ value.title }}
              </h4>

              <p class="text-neutral-500 text-base font-normal">
                {{ value.description }}
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>