<template>
  <div class="t-announcement" v-show="props.showAnnouncement">
    <div class="container h-100">
        <swiper
          :slides-per-view="props.slidePerView"
          :space-between="props.spaceBetween"
          :navigation="props.navigation"
          :modules="props.modules"
          :pagination="props.pagination"
          :autoplay="props.autoplay"
          loop
        >
            <swiper-slide v-for="(item, index) in props.slideItems"
                          :key="index">
              <div class="t-announcement__content t-flex justify-center align-center h-100 col-gap-10">
                <div v-html="item.icon" class="icon"></div>
                <h6>{{ item.title }}</h6>
              </div>
            </swiper-slide>
        </swiper>
    </div>
    <div class="t-announcement__close" @click="handleClose">
      <svg class="t-svg-icon--medium" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
      </svg>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue'
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from 'swiper/vue'
import { Navigation, Pagination, Scrollbar, A11y, Autoplay  } from 'swiper/modules'

import 'swiper/scss';
import 'swiper/scss/autoplay';
const emit = defineEmits(['closeAnnouncement'])

const handleClose = () => {
  emit('closeAnnouncement', false);
}
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
    default: () => [Navigation, Pagination, Scrollbar, A11y, Autoplay ]
  },
  pagination: {
    type: Object,
    default: () => ({
      clickable: true
    })
  },
  slideItems: {
    type: Array,
    default: () => []
  },
  autoplay: {
    type: Object,
    default: () => ({
      delay: 3000, 
      disableOnInteraction: false
    })
  },
  showAnnouncement: {
    type: Boolean,
    default: true
  }
})
</script>

<style lang="scss" scoped>
  .container {
    --container-width: 600px;
  }
  h6 {
    --heading-margin-bottom-desktop: 0;
    --heading-margin-bottom-mobile: 0;
    font-weight: 500;
  }

  .t-announcement {
    background-color: var(--anouncementBg);
    color: var(--anouncementColor);
    --swiper-navigation-color: var(--anouncementColor);
    position: relative;

    &__content {
      min-height: 40px;
    }

    &__close {
      position: absolute;
      top: 10px;
      right: 10px;
      cursor: pointer;
    }
  }
</style>