<template>
  <div class="t-slider">
    <div class="container-full h-100">
      <swiper
        :slides-per-view="props.slidePerView"
        :space-between="props.spaceBetween"
        :navigation="props.navigation"
        :modules="props.modules"
        :pagination="props.pagination"
        :autoplay="props.autoplay"
        :effect="'fade'"
        :parallax="true"
        :direction="'vertical'"
        loop
        class="h-100"
      >
        <swiper-slide v-for="(item, index) in props.slideItems" :key="index">
          <div class="t-slider__wrapper">
            <img :src="getImageUrl(item.image)" alt="" />
            <div class="t-slider__content-container overlay">
              <div class="t-slider__content text-white">
                <p class="t-subtitle t-slider__sub-title">
                  {{ item.subtitle }}
                </p>
                <h2 class="h3">{{ item.title }}</h2>
                <div class="t-slider__description">
                  <p>
                    {{ item.description }}
                  </p>
                </div>
                <div class="t-slider__btn mt-32">
                  <a class="btn">Xem chi tiết</a>
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
    default: false
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
const getImageUrl = (name) => {
  return new URL(`../../assets/images/slider/${name}`, import.meta.url).href
}
</script>

<style lang="scss">
@import '@/assets/scss/ultinities/breakpoints';
.t-slider {
  width: 100%;
  overflow: hidden;
  height: 600px;
  @include breakpoint-min(md) {
    height: 703px;
  }

  @include breakpoint-max(md) {
  --swiper-pagination-right: 24px;

  }

  .swiper-button-prev,
  .swiper-button-next {
    --swiper-navigation-size: 28px !important;
  }

  --swiper-navigation-color: #ffffff;
  &__wrapper {
    width: 100%;
    height: 100%;
    position: relative;

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
    padding: 60px 24px;
    display: flex;
    justify-content: flex-start;
    z-index: 99;
    @include breakpoint-min(md) {
      padding: 100px 65px;
    }
  }

  &__content {
    max-width: 400px;
    width: max-content;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    transition: all 0.8s;
    transform: translateY(0);
    h2 {
      font-family: 'T-Font-Regular', sans-serif;
      color: #ffffff;
    }
  }

  &__description {
    max-width: 80%;
    p {
      margin-bottom: 0;
      line-height: 1.5;
    }
  }

  &__btn {
    .btn {
      pointer-events: all;
    }
  }

  .swiper-slide-active {
    .t-slider__content {
      transform: translateY(-20px);
    }
  }
  // .swiper-pagination-bullet-active {
  //    --swiper-pagination-bullet-size: 20px;
  //   --swiper-pagination-bullet-width: 20px;
  //   --swiper-pagination-bullet-height: 20px;
  // }
}
</style>