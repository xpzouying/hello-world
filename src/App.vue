<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import ShowcaseSection from './components/ShowcaseSection.vue'
import CtaSection from './components/CtaSection.vue'
import FooterBar from './components/FooterBar.vue'
</script>

<template>
  <NavBar />
  <main>
    <HeroSection />
    <FeaturesSection />
    <ShowcaseSection />
    <CtaSection />
  </main>
  <FooterBar />
</template>
