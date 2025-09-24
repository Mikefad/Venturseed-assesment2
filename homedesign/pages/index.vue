<template>
  <main class="min-h-screen bg-white">
    <SiteNavbar />
    <HeroSection />
    <TrustedBy />
    <SectionHeadingWhatIs/>
    <SectionControlPanel/>
    <SectionOpenFeature/>
    <control/>
    <dart/>
    <aiSection/>
    <paymentplan/>
    <whysection/>
    <pricingdiv/>
    <Footer />

  </main>
</template>

<script setup lang="ts">
import SiteNavbar from '~/components/Navbar.vue'
import HeroSection from '~/components/Hero.vue'
import TrustedBy from '~/components/TrustedBy.vue'
import SectionControlPanel from '~/components/SectionControlPanel.vue'
import SectionHeadingWhatIs from '~/components/SectionHeadingWhatIs.vue'
import SectionOpenFeature from '~/components/SectionOpenFeature.vue'
import control from '~/components/control.vue'
import dart from '~/components/dart.vue'
import aiSection from '~/components/ai-section.vue'
import paymentplan from '~/components/paymentplan.vue'
import whysection from '~/components/whysection.vue'
import Footer from '~/components/footer.vue'
import pricingdiv from '~/components/pricingdiv.vue'
</script>
