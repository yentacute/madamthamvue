<template>
  <div class="section t-information">
    <div class="container">
      <div class="t-information__wrapper" :class="props.classes">
        <div class="t-information__img">
          <slot name="img"></slot>
        </div>
        <div class="t-information__content">
          <slot name="content"></slot>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  classes: {
    type: String,
    default: 'flex align-center'
  }
})
</script>

<style lang="scss">
@import '@/assets/scss/ultinities/breakpoints';
@import '@/assets/scss/components/readmore.scss';
</style>