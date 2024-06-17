<template>
  <div class="section t-information">
    <div class="container">
      <div class="t-information__wrapper t-flex align-center">
        <div class="t-information__img">
          <img src="@/assets/images/readmore/1.jpeg" alt="">
        </div>
        <div class="t-information__content">
          <h2>Dịch Vụ Vệ Sinh Gleam & Shine</h2>
          <div class="t-informatiion__description">
            <p>
               Cung cấp dịch vụ vệ sinh xuất sắc làm cho ngôi nhà của bạn trở nên lấp lánh. Đội ngũ vệ sinh chuyên nghiệp của chúng tôi sử dụng các sản phẩm và kỹ thuật chất lượng cao nhất để đảm bảo không gian sống của bạn sáng bóng và sạch sẽ, làm cho ngôi nhà trở nên tươi sáng và thân thiện hơn."
            </p>
          </div>
          <div class="t-information__button">
            <a href="" class="btn t-btn-primary">Đọc thêm</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>

</script>

<style lang="scss" scoped>
  .t-information {
    &__wrapper {
      column-gap: var(--t-information-wrapper-column-gap, 60px);
    }

    &__button {
      margin-top: var(--t-information-button-margin-top, 32px);
    }
    h2 {
      max-width: 96%;
    }
  }
</style>