<script setup>
import MenuCard from './components/MenuCard.vue'
import HeroSection from './components/HeroSection.vue'
import AboutSection from './components/AboutSection.vue'
import ProjectSection from './components/ProjectSection.vue'
import ContactSection from './components/ContactSection.vue'
import FooterSection from './components/FooterSection.vue'

</script>

<template>
  <header>
    <Transition name="slide">
    <MenuCard/>
    </Transition>
  </header>
  <main>
    <HeroSection name="AMON" />
    <AboutSection/>
    <ProjectSection/>
    <ContactSection/>
    <FooterSection/>
  </main>
</template>

<style lang="css" scoped>
@media (max-width: 769px) {
  
.slide-enter-active, .slide-leave-active {
  transition: transform 0.5s ease-in-out;
}
.slide-enter-from {
  transform: translateX(-100%);
}
.slide-leave-to {
  transform: translateX(-100%);
}
}

</style>

