<template>
  <section class="t-image-with-text section">
    <div :class="props.container">
      <div class="t-image-with-text__wrapper  md:row-gap-24 col-gap-60 row-gap-60" :class="props.classes">
        <div class="t-image-with-text__content" :class="props.classAlign">
          <h2 class="h3">Sống tươi đẹp, chăm sóc từng góc nhỏ của nhà.</h2>
          <a href="" class="t-link">Xem chi tiết</a>
        </div>

        <div class="t-image-with-text__image">
          <img class="image-full" src="../assets/images/image-with-text/3.webp" alt="" />
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  classes: {
    type: String,
    default: 'flex flex-column'
  },

  container: {
    type: String,
    default: 'container'
  },
  classAlign: {
    type: String,
    default: 'flex flex-column justify-center align-center text-center'
  }
})
</script>

<style lang="scss">
.t-image-with-text {
  --t-link-py: 5px;
  &__content {
    h2 {
      max-width: 80%;
    }
  }

  .t-link {
    font-family: 'T-Font-Heading', sans-serif;
    font-weight: 600;
    color: var(--t-subtitle-color);
    --t-link-underline-color: var(--t-subtitle-color);
    font-size: 18px;
  }

  &__image {
    min-height: 600px;
    position: relative;
  }
}
</style>