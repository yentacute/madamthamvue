<template>
  <section class="section t-multiple-cols">
    <div class="container">
      <div class="t-multiple__wrapper">
        <div class="grid grid-3-cols  md:grid-1-cols md:row-gap-30" style="--column-gap: 48px; --column-gap-mobile: 30px">
          <div class="t:column t-icon-box__inner flex flex-column justify-center align-center row-gap-24">
            <div class="t-icon-box__img">
              <img src="@/assets/images/icons/time.png" alt="" />
            </div>
            <div class="t-icon-box__content text-center">
              <h3 class="h5">Tiết Kiệm Thời Gian</h3>
              <div class="t-icon-box__description">
                <p>
                  Thay vì dành thời gian dọn dẹp, bạn có thể tập trung vào những công việc quan
                  trọng khác.
                </p>
              </div>
            </div>
          </div>
          <div class="t:column t-icon-box__inner flex flex-column justify-center align-center row-gap-24">
            <div class="t-icon-box__img">
              <img src="@/assets/images/icons/save-money.png" alt="" />
            </div>
            <div class="t-icon-box__content text-center">
              <h3 class="h5">Gói Dịch Vụ Ưu Đãi</h3>
              <div class="t-icon-box__description">
                <p>
                  Nhiều công ty cung cấp các gói dịch vụ dài hạn với mức giá hấp dẫn, giúp bạn
                  tiết kiệm hơn.
                </p>
              </div>
            </div>
          </div>
          <div class="t:column t-icon-box__inner flex flex-column justify-center align-center row-gap-24">
            <div class="t-icon-box__img">
              <img src="@/assets/images/icons/fast.png" alt="" />
            </div>
            <div class="t-icon-box__content text-center">
              <h3 class="h5">Nâng Cao Chất Lượng Cuộc Sống</h3>
              <div class="t-icon-box__description">
                <p>
                  Nâng cao chất lượng cuộc sống hàng ngày mà còn tạo môi trường tràn đầy năng
                  lượng.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>

</script>

<style lang="scss" scoped>
@keyframes tZoomEffect {
  0% {
    opacity: 0.8;
    transform: scale(1.1);
  }
  100% {
    opacity: 1;
    transform: scale(1);
  }
}

.t-multiple__wrapper {
  .t-icon-box {
    &__img {
      max-width: 80px;
      margin: 0 auto;
      overflow: hidden;
      cursor: pointer;
      transition: transform 0.3s ease-out, opacity 0.3s ease-out;
      will-change: transform, opacity;

      &:hover {
        transform: scale(1.1);
        opacity: 0.9;
      }

      img {
        width: 100%;
      }
    }
  }
  .h5 {
    --heading-margin-bottom-desktop: 12px;
  }
}
</style>