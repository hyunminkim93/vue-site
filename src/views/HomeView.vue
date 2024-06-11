<script setup lang="ts">
import HeaderSection from '@/components/HeaderSection.vue'
import SkipSection from '@/components/SkipSection.vue'
import IntroSection from '@/components/IntroSection.vue'
import SkillSection from '@/components/SkillSection.vue'
import SiteSection from '@/components/SiteSection.vue'
import PortSection from '@/components/PortSection.vue'
import ContactSection from '@/components/ContactSection.vue'
import FooterSection from '@/components/FooterSection.vue'
</script>

<template>
  <SkipSection />
  <HeaderSection />
  <main id="main" role="main">
    <IntroSection />
    <SkillSection />
    <SiteSection />
    <PortSection />
    <ContactSection />
  </main>
  <FooterSection />
</template>
