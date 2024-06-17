<template>
  <LayoutComponent>
<<<<<<< HEAD
    <HomeSlider
      :slide-items="slideData"
=======
    <HomeSlider 
      :slide-items="slideData" 
>>>>>>> 082767e8fedfdde2cd576c4cda7ae244e99d53a9
      :space-between="0"
      :autoplay="true"
      :pagination="{
        clickable: true,
        verticalClass: 'swiper-pagination-vertical'
      }"
<<<<<<< HEAD
    />
    <Information />

    <MultipleColumns />
=======
       />  
       fdufheu
>>>>>>> 082767e8fedfdde2cd576c4cda7ae244e99d53a9
  </LayoutComponent>
</template>

<script setup>
import LayoutComponent from '../components/layout/index.vue'
import HomeSlider from '../components/slide/HomeSlider.vue'
import slideData from '../data/slide.json'
<<<<<<< HEAD
import Information from '../components/readmore/index.vue'
import MultipleColumns from '../components/MultipleColumns.vue'
=======
>>>>>>> 082767e8fedfdde2cd576c4cda7ae244e99d53a9
</script>

<style lang="scss" scoped>
</style>