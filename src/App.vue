<script setup>
import NavBar from './components/NavBar.vue'
import HeroSection from './components/HeroSection.vue'
import StatsBar from './components/StatsBar.vue'
import AboutSection from './components/AboutSection.vue'
import MenuSection from './components/MenuSection.vue'
import ReviewsSection from './components/ReviewsSection.vue'
import ReserveSection from './components/ReserveSection.vue'
import FooterBar from './components/FooterBar.vue'
</script>

<template>
  <NavBar />
  <main>
    <HeroSection />
    <StatsBar />
    <AboutSection />
    <MenuSection />
    <ReviewsSection />
    <ReserveSection />
  </main>
  <FooterBar />
</template>
