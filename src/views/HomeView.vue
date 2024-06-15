<template>
  <LayoutComponent>
    <HomeSlider 
      :slide-items="slideData" 
      :space-between="0"
      :autoplay="true"
      :pagination="{
        clickable: true,
        verticalClass: 'swiper-pagination-vertical'
      }"
       />  
       fdufheu
  </LayoutComponent>
</template>

<script setup>
import LayoutComponent from '../components/layout/index.vue'
import HomeSlider from '../components/slide/HomeSlider.vue'
import slideData from '../data/slide.json'
</script>

<style lang="scss" scoped>
</style>