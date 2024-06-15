<template>
  <div class="t-slider">
    <div class="container-full">
      <swiper
        :slides-per-view="props.slidePerView"
        :space-between="props.spaceBetween"
        :navigation="props.navigation"
        :modules="props.modules"
        :pagination="props.pagination"
        :scrollbar="props.scrollbar"
        :autoplay="props.autoplay"
        :effect="'fade'"
        :parallax="true"
        loop
      >
        <swiper-slide v-for="(item, index) in props.slideItems" :key="index">
          <div class="t-slider__wrapper">
            <img :src="item.image" alt="" />
            <div class="t-slider__content-container">
              <div class="t-slider__content text-white">
                <p class="t-subtitle t-slider__sub-title">
                  {{ item.subtitle }}
                </p>
                <h1>{{ item.title }}</h1>
                <div class="t-slider__description">
                  {{ item.description }}
                </div>
                <div class="t-slider__btn mt-32">
                  <a class="btn">Shop Now</a>
                </div>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'
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
    type: Boolean,
    default: true
  },
  modules: {
    type: Array,
    default: () => [Navigation, Pagination, Scrollbar, A11y, Autoplay, EffectFade, EffectCoverflow]
  },
  pagination: {
    type: Object,
    default: () => ({
      clickable: true,
      verticalClass: 'swiper-pagination-vertical'
    })
  },
  slideItems: {
    type: Array,
    default: () => []
  },
  autoplay: {
    type: Object,
    default: () => ({
      delay: 4000,
      disableOnInteraction: false
    })
  },
  effect: {
    type: String,
    default: 'fade'
  }
})
</script>

<style lang="scss">
.t-slider {
  width: 100%;

  .swiper-button-prev,
  .swiper-button-next {
    --swiper-navigation-size: 28px !important;
  }

  --swiper-navigation-color: #ffffff;
  &__wrapper {
    width: 100%;
    position: relative;
    overflow: hidden;
    height: 703px;

    img {
      position: absolute;
      width: 100%;
      height: 100%;
      left: 0%;
      right: 0;
      top: 0;
      bottom: 0;
      object-fit: cover;
      z-index: 10;
    }
  }

  &__content-container {
    width: 100%;
    height: 100%;
    position: absolute;
    left: 0;
    top: 0;
    padding: 100px 65px;
    display: flex;
    justify-content: flex-start;
    z-index: 99;
    transition: all 0.3s;
  }

  &__content {
    max-width: 500px;
    width: max-content;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }
}
</style>