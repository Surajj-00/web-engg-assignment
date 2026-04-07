<script setup>
import { RouterLink, RouterView } from 'vue-router'
import Navbar from './components/layout/Navbar.vue'
import HeroSection from './components/sections/HeroSection.vue'
import AnalyticsConvergence from './components/sections/AnalyticsConvergence.vue';
import ServiceGrid from './components/sections/ServiceGrid.vue';
import StatSection from './components/sections/StatSection.vue';
import FaqSection from './components/sections/FaqSection.vue';
import CtaSection from './components/sections/CtaSection.vue';
import Footer from './components/layout/Footer.vue';
</script>

<template>
  <div class="pt-16 container-main">
    <Navbar />
    <HeroSection />
    <AnalyticsConvergence/>
    <ServiceGrid/>
    <StatSection/>
    <FaqSection/>
    <CtaSection/>
    <Footer/>
  </div>
</template>
