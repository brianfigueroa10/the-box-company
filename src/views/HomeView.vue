<script setup>
import Hero from '@/components/HomePage/Hero.vue'
import About from '@/components/HomePage/About.vue'
import Services from '@/components/HomePage/Services.vue'
import Stats from '@/components/HomePage/Stats.vue'
import Ads from '@/components/HomePage/Ads.vue'
import Projects from '@/components/HomePage/Projects.vue'
import ContactForm from '@/components/HomePage/ContactForm.vue'
</script>

<template>
  <main class="mt-10">
    <Hero />
    <Stats />
    <Services />
    <About />
    <Ads />
    <Projects />
    <ContactForm />
  </main>
</template>
