<script setup lang="ts">
  import { ref } from 'vue'
  import { 
    House, 
    UserRound,
    GalleryVerticalEnd,
    Book 
  } from 'lucide-vue-next'
  import Header from './components/global/Header.vue'
  import HeroSection from './components/partials/HeroSection.vue'
  import AboutSection from './components/partials/AboutSection.vue'
  import ProjectsSection from './components/partials/ProjectsSection.vue'
  import ContactSection from './components/partials/ContactSection.vue'

  const sectionsData = [
    {
      id: 'hero',
      icon: House,
      label: 'Início',
      component: HeroSection
    },
    {
      id: 'about',
      icon: UserRound,
      label: 'Sobre',
      component: AboutSection
    },
    {
      id: 'projects',
      icon: GalleryVerticalEnd,
      label: 'Projetos',
      component: ProjectsSection
    },
    {
      id: 'contact',
      icon: Book,
      label: 'Contato',
      component: ContactSection
    }
  ]

  const currentSection = ref(sectionsData[0]?.id)
</script>

<template>
  <div class="relative">
    <Header
      :items="sectionsData"
      v-model:current="currentSection"
    />

    <main class="min-h-screen">
      <transition
        name="fade" 
        mode="out-in"
      >
        <component
          :is="sectionsData.find(section => section.id === currentSection)?.component"
          :key="currentSection"
        />
      </transition>
    </main>
  </div>
</template>

<style>
  .fade-enter-active,
  .fade-leave-active {
    transition: opacity 0.3s;
  }
  .fade-enter-from,
  .fade-leave-to {
    opacity: 0;
  }
</style>