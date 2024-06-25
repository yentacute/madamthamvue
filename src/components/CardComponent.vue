<template>
  <div class="t-card__product">
    <div class="t-card__product-media">
      <a href="" class="t-card__link"></a>
      <div class="t-card__product-image">
        <img :src="getImageUrl(props.item.image)" alt="" />
      </div>
      <div class="t-card__product-action">
        <button class="icon-action">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
            <path
              d="M288 80c-65.2 0-118.8 29.6-159.9 67.7C89.6 183.5 63 226 49.4 256c13.6 30 40.2 72.5 78.6 108.3C169.2 402.4 222.8 432 288 432s118.8-29.6 159.9-67.7C486.4 328.5 513 286 526.6 256c-13.6-30-40.2-72.5-78.6-108.3C406.8 109.6 353.2 80 288 80zM95.4 112.6C142.5 68.8 207.2 32 288 32s145.5 36.8 192.6 80.6c46.8 43.5 78.1 95.4 93 131.1c3.3 7.9 3.3 16.7 0 24.6c-14.9 35.7-46.2 87.7-93 131.1C433.5 443.2 368.8 480 288 480s-145.5-36.8-192.6-80.6C48.6 356 17.3 304 2.5 268.3c-3.3-7.9-3.3-16.7 0-24.6C17.3 208 48.6 156 95.4 112.6zM288 336c44.2 0 80-35.8 80-80s-35.8-80-80-80c-.7 0-1.3 0-2 0c1.3 5.1 2 10.5 2 16c0 35.3-28.7 64-64 64c-5.5 0-10.9-.7-16-2c0 .7 0 1.3 0 2c0 44.2 35.8 80 80 80zm0-208a128 128 0 1 1 0 256 128 128 0 1 1 0-256z"
            />
          </svg>
        </button>
        <button class="icon-action">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512">
            <path
              d="M0 24C0 10.7 10.7 0 24 0H69.5c22 0 41.5 12.8 50.6 32h411c26.3 0 45.5 25 38.6 50.4l-41 152.3c-8.5 31.4-37 53.3-69.5 53.3H170.7l5.4 28.5c2.2 11.3 12.1 19.5 23.6 19.5H488c13.3 0 24 10.7 24 24s-10.7 24-24 24H199.7c-34.6 0-64.3-24.6-70.7-58.5L77.4 54.5c-.7-3.8-4-6.5-7.9-6.5H24C10.7 48 0 37.3 0 24zM128 464a48 48 0 1 1 96 0 48 48 0 1 1 -96 0zm336-48a48 48 0 1 1 0 96 48 48 0 1 1 0-96zM252 160c0 11 9 20 20 20h44v44c0 11 9 20 20 20s20-9 20-20V180h44c11 0 20-9 20-20s-9-20-20-20H356V96c0-11-9-20-20-20s-20 9-20 20v44H272c-11 0-20 9-20 20z"
            />
          </svg>
        </button>
      </div>
      <div class="t-card__product-atc">
        <a href="/abc" class="btn btn-atc text-center">Thêm vào giỏ hàng</a>
      </div>
    </div>
    <div class="t-card__product-content">
      <h3 class="t-card__product-name h5">
        <a href="">{{ props.item.name }}</a>
      </h3>
      <div class="t-card__product-price">
        {{ props.item.price }}
      </div>
      <div class="t-card__product-variants">
        <div class="t-card__product-watch">
          <label
            class="t-card__product--node__label"
            style="background: rgb(225, 211, 188)"
          ></label>
        </div>
        <div class="t-card__product-watch">
          <label class="t-card__product--node__label" style="background: rgb(131, 105, 83)"></label>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue'
const props = defineProps({
  item: {
    type: Object,
    required: true
  }
})

const getImageUrl = (name) => {
  return new URL(`../assets/images/product/1/${name}`, import.meta.url).href
}
</script>

<style lang="scss" scoped>
@import '@/assets/scss/components/card.scss';
</style>