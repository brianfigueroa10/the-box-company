<script setup>
import { RouterView } from 'vue-router'

import Navbar from './layout/Navbar.vue'
import Footer from './layout/Footer.vue'
import ContactForm from './components/HomePage/ContactForm.vue'
</script>

<template>
  <Navbar />
  <RouterView />
  <ContactForm />
  <Footer />
</template>
