<template>
  <section class="t-footer section">
    <div class="container">
      <div class="t-footer__wrapper">
        <div class="t-footer__content flex md:flex-column  flex-wrap md:row-gap-24">
          <div
            class="t-footer__block t-footer__block--info md:w-100 w-3-12  flex flex-column align-start justify-start"
          >
            <div class="t-footer__logo">
              <img src="../../assets/images/logo.png" alt="logo" />
            </div>
            <div class="t-footer__form">
              <h3 class="t-footer__menu-title h5">Đừng bỏ lỡ cơ hội</h3>
              <p>Theo dõi chúng tôi để biết thêm nhiều ưu đãi.</p>
              <EmailSubcribe />
            </div>
          </div>
          <div class="md:w-0 w-1-12"></div>
          <div class="t-footer__block md:w-100 w-2-12">
            <div class="t-footer__menu">
              <h3 class="t-footer__menu-title h5">Dịch vụ</h3>
              <ul>
                <li><a href="#">Dọn dẹp nhà cửa</a></li>
                <li><a href="#">Chăm sóc thú cưng</a></li>
                <li><a href="#">Sản phẩm</a></li>
                <li><a href="#">Liên hệ</a></li>
              </ul>
            </div>
          </div>

          <div class="t-footer__block md:w-100 w-2-12">
            <div class="t-footer__menu">
              <h3 class="t-footer__menu-title h5">Về chúng tôi</h3>
              <ul>
                <li><a href="#">Giới thiệu</a></li>
                <li><a href="#">Liên hệ</a></li>
                <li><a href="#">Đội ngũ nhân viên</a></li>
                <li><a href="#">Tin tức và sự kiện</a></li>
              </ul>
            </div>
          </div>
          <div class="t-footer__block md:w-100 w-2-12">
            <div class="t-footer__menu">
              <h3 class="t-footer__menu-title h5">Liên kết hữu ích</h3>
              <ul>
                <li><a href="#">Blog</a></li>
                <li><a href="#">Đối tác</a></li>
                <li><a href="#">Tuyển dụng</a></li>
                <li><a href="#">FAQ</a></li>
              </ul>
            </div>
          </div>

          <div class="t-footer__block md:w-100 w-2-12">
            <div class="t-footer__contact">
              <h3 class="t-footer__menu-title h5">Liên hệ</h3>
              <IconSocials :wrapperClass="'flex align-center col-gap-12'" />
            </div>
          </div>
        </div>
      </div>
      <div class="t-footer__copyright flex justify-center align-center">
        <p>© 2020 All rights reserved</p>
      </div>
    </div>
  </section>
</template>

<script setup>
import IconSocials from '../icons/IconSocials.vue'
import EmailSubcribe from '../EmailSubcribe.vue'
</script>

<style lang="scss" scoped>
@import '../../assets/scss/layout/footer.scss';
</style>