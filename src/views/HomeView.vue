<template>
  <LayoutComponent>
    <HomeSlider :slide-items="slideData" :space-between="0" :autoplay="true" />
    <MultipleColumns />
    <ProductSlider
      :slide-per-view="4"
      :space-between="30"
    />
    <Information :classes="'md:t-flex-column'">
      <template v-slot:img>
        <img src="@/assets/images/readmore/1.jpeg" alt="">
      </template>

      <template v-slot:content>
          <h2>Dịch Vụ Vệ Sinh Gleam & Shine</h2>
          <div class="t-informatiion__description">
            <p>
              Cung cấp dịch vụ vệ sinh xuất sắc làm cho ngôi nhà của bạn trở nên lấp lánh. Đội ngũ vệ sinh chuyên nghiệp của chúng tôi sử dụng các sản phẩm và kỹ thuật chất lượng cao nhất để đảm bảo không gian sống của bạn sáng bóng và sạch sẽ, làm cho ngôi nhà trở nên tươi sáng và thân thiện hơn."
            </p>
          </div>
          <div class="t-information__button">
            <a href="" class="btn t-btn-primary">Đọc thêm</a>
          </div>
      </template>
    </Information>
    <ContactFormVue />
    <Information :classes="'t-flex align-center t-flex-row-reverse'">
      <template v-slot:img>
        <img class="w-100 h-100" src="@/assets/images/readmore/pet.webp" alt="">
      </template>

      <template v-slot:content>
          <h2>Giúp Thú Cưng Vui Chơi Và Tập Luyện</h2>
          <div class="t-informatiion__description">
            <p>
              Khám phá những hoạt động vui chơi và bài tập luyện thú vị giúp thú cưng của bạn luôn khỏe mạnh, năng động và không bị nhàm chán.
            </p>
          </div>
          <div class="t-information__button">
            <a href="" class="btn t-btn-primary">Đọc thêm</a>
          </div>
      </template>
    </Information>
    <ProductSlider
      :slide-per-view="4"
      :space-between="30"
    />
    <CompareImageVue />
    
    <ImageWithText/>

    
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
import ImageWithText from '@/components/ImageWithText.vue'
import ProductSlider from '@/components/ProductSlider.vue'
</script>

<style lang="scss" scoped>
</style>