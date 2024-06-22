<template>
  <section class="t-product-card__slider section">
    <div class="container">
      <swiper
        :slides-per-view="props.slidePerView"
        :space-between="props.spaceBetween"
        :navigation="props.navigation"
        :modules="props.modules"
        :pagination="props.pagination"
        :autoplay="props.autoplay"
        loop
      >
        <swiper-slide v-for="(item, index) in data" :key="index">
          <CardComponent :item="item"/>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue'
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'

import CardComponent from '@/components/CardComponent.vue'
import {
  Navigation,
  Pagination,
  Scrollbar,
  A11y,
  Autoplay,
  EffectFade,
  EffectCoverflow
} from 'swiper/modules'

import 'swiper/scss'
import 'swiper/scss/autoplay'
import 'swiper/css/effect-fade'
import 'swiper/css/effect-coverflow'
import 'swiper/css/pagination'


const data = [
  {
    name: 'Dụng cụ tưới cây',
    image: '1.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '2.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '3.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '4.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '1.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '2.webp',
    price: '$10.0'
  },
  {
    name: 'Dụng cụ tưới cây',
    image: '3.webp',
    price: '$10.0'
  }
]

const props = defineProps({
  slidePerView: {
    type: Number,
    default: 1
  },
  spaceBetween: {
    type: Number,
    default: 30
  },
  navigation: {
    type: Object,
    default: () => ({
      enabled: true

    })
  },
  modules: {
    type: Array,
    default: () => [Navigation, Pagination, Scrollbar, A11y, Autoplay, EffectFade, EffectCoverflow]
  },
  pagination: {
    type: Object,
    default: () => ({
      clickable: true,
      verticalClass: 'swiper-pagination-vertical',
      type: 'bullets'
    })
  },
  slideItems: {
    type: Array,
    default: () => []
  },
  autoplay: {
    type: Boolean,
    default: false
  },
  effect: {
    type: String,
    default: 'fade'
  }
})

</script>

<style lang="scss">
  .swiper-pagination-bullet {
    --swiper-pagination-bullet-inactive-color: rgba(34, 34, 34, .3);
    --swiper-pagination-bullet-size: 10px;
  }
  .swiper {
    padding-bottom: 60px;
  }
  .swiper-button-prev,
  .swiper-button-next {
    --swiper-navigation-top-offset: 35%;
    background-color: rgb(var(--t-btn-secondary-bg));
    border-radius: 50px;
    transition: all var(--t-duration-default, .25s) ease;
    color: rgb(var(--t-btn-secondary-color));

    &:hover {
      background-color: rgb(var(--t-btn-bg-hover));
      color: rgb(var(--t-btn-text-color-hover));
    }

  }

  .swiper-button-prev {
    transform: translate3d(-150%, 0 ,0);
    opacity: 0;
  }

  .swiper-button-next {
    transform: translate3d(150%, 0, 0);
    opacity: 0;
  }
  .swiper-button-prev:after, .swiper-button-next:after {
    --swiper-navigation-size: 13px;
  }

  .swiper {
    transition: all var(--t-duration-default) ease;
    &:hover {
      .swiper-button-prev,
      .swiper-button-next {
        opacity: 1;
        transform: translateX(0);
      }
    }
  }
</style>