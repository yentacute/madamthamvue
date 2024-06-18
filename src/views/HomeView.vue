<template>
  <LayoutComponent>
    <HomeSlider
      :slide-items="slideData"
      :space-between="0"
      :autoplay="true"
    />
    <Information />

    <MultipleColumns />
    <CompareImageVue/>
    <ContactFormVue/>
  </LayoutComponent>
</template>

<script setup>
import LayoutComponent from '../components/layout/index.vue'
import HomeSlider from '../components/slide/HomeSlider.vue'
import slideData from '../data/slide.json'
import Information from '../components/readmore/index.vue'
import MultipleColumns from '../components/MultipleColumns.vue'
import CompareImageVue from '@/components/CompareImage.vue'
import ContactFormVue from '@/components/ContactForm.vue'


</script>

<style lang="scss" scoped>
</style>