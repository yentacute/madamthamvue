<template>
  <header class="t-header">
    <SlideAnnouncement 
      :slide-items="announcements" 
      :pagination="false"
      :space-between="0"
      @closeAnnouncement="handleClose"
      :showAnnouncement = showAnnouncement
       />
    <div class="container">
      <div class="t-header__wrapper t-flex align-center">
        <div class="t-header__logo w-2-12 t-flex justify-start">
          <a href="">
            <img src="../../assets/images/logo.png" alt="" />
          </a>
        </div>
        <div class="t-header__menu w-8-12 t-flex justify-center">
          <ul class="t-menu__list t-flex">
            <li class="t-menu">
              <a href="" class="t-menu__parent t-link">Trang chủ</a>
            </li>
            <li class="t-menu t-menu__has-sub">
              <a href="" class="t-menu__parent t-link">
                <span class="t-menu__title">Dịch vụ</span>
                <svg class="t-svg-icon--small" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" fill="#222" version="1.1" id="Layer_1" viewBox="0 0 407.437 407.437" xml:space="preserve">
                  <polygon points="386.258,91.567 203.718,273.512 21.179,91.567 0,112.815 203.718,315.87 407.437,112.815 "/>
                </svg>
                <svg class="t-svg-icon--custom" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" role="img" aria-labelledby="chevronUpIconTitle" stroke="#222" stroke-width="1" stroke-linecap="square" stroke-linejoin="miter" fill="none" color="#222"> <title id="chevronUpIconTitle">Chevron Up</title> <polyline points="6 14 12 8 18 14 18 14"/> </svg>
              </a>
              <ul class="t-menu__sub-menu">
                <li class="t-menu__sub-menu-item">
                  <a href="">{{ menu.HomeCleanServices.title }}</a>
                  <ul class="t-menu__sub-child">
                    <li v-for="(item, index) in menu.HomeCleanServices.submenus" :key="index" class="t-menu__sub-child-item" >
                      <a href="">{{ item.title }}</a>
                    </li>
                  </ul>
                </li>
                <li class="t-menu__sub-menu-item">
                  <a href="">{{ menu.PetCareServices.title }}</a>
                  <ul class="t-menu__sub-child">
                    <li v-for="(item, index) in menu.PetCareServices.submenus" :key="index" class="t-menu__sub-child-item" >
                      <a href="">{{ item.title }}</a>
                    </li>
                  </ul>
                </li>
              </ul>
            </li>
            <li class="t-menu t-menu__has-sub">
              <a href="" class="t-menu__parent t-link">Shop</a>
              <ul class="t-menu__sub-menu">
                <li v-for="(item, index) in menu.shop" :key="index" class="t-menu__sub-menu-item">
                  <a href="">{{ item.title }}</a>
                </li>
              </ul>
            </li>
            <li class="t-menu">
              <a href="" class="t-menu__parent t-link">Liên hệ</a>
            </li>
            <li class="t-menu">
              <a href="" class="t-menu__parent t-link">Về chúng tôi</a>
            </li>
          </ul>
        </div>

        <div class="t-header__right w-2-12 t-flex justify-end">
          <a href="">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 448 512"
              class="t-svg-icon--medium"
            >
              <path
                d="M304 128a80 80 0 1 0 -160 0 80 80 0 1 0 160 0zM96 128a128 128 0 1 1 256 0A128 128 0 1 1 96 128zM49.3 464H398.7c-8.9-63.3-63.3-112-129-112H178.3c-65.7 0-120.1 48.7-129 112zM0 482.3C0 383.8 79.8 304 178.3 304h91.4C368.2 304 448 383.8 448 482.3c0 16.4-13.3 29.7-29.7 29.7H29.7C13.3 512 0 498.7 0 482.3z"
              />
            </svg>
          </a>
          <a href="">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 512 512"
              class="t-svg-icon--medium"
            >
              <path
                d="M416 208c0 45.9-14.9 88.3-40 122.7L502.6 457.4c12.5 12.5 12.5 32.8 0 45.3s-32.8 12.5-45.3 0L330.7 376c-34.4 25.2-76.8 40-122.7 40C93.1 416 0 322.9 0 208S93.1 0 208 0S416 93.1 416 208zM208 352a144 144 0 1 0 0-288 144 144 0 1 0 0 288z"
              />
            </svg>
          </a>
        </div>
      </div>
    </div>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import SlideAnnouncement from '../slide/AnnouncementSlide.vue'
import menu from '../../data/menu.json'
const announcements = ref([
  {
    title: 'Get 20% Off Your First Cleaning Service!',
    icon: "<svg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='currentColor' stroke-width='2'><path stroke-linecap='round' stroke-linejoin='round' d='M4 12h16M4 12l4 4m-4-4l4-4' /></svg>"
  },
  {
    title: 'Eco-Friendly Cleaning Solutions!',
    icon: "<svg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='currentColor' stroke-width='2'><path stroke-linecap='round' stroke-linejoin='round' d='M12 8v8m4-4H8' /></svg>"
  },
  {
    title: 'Exclusive Pet Care Packages Available!',
    icon: "<svg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='currentColor' stroke-width='2'><path stroke-linecap='round' stroke-linejoin='round' d='M10 15v4a2 2 0 002 2h0a2 2 0 002-2v-4m-8 0v4a2 2 0 002 2h0a2 2 0 002-2v-4m6-8l.3-.6a2 2 0 00-1.8-2.8h0a2 2 0 00-1.8 2.8l.3.6m2 0l-.3-.6a2 2 0 00-1.8-2.8h0a2 2 0 00-1.8 2.8l.3.6' /></svg>"
  }
])

const showAnnouncement = ref(true);
const activeHover = ref(false);

const handleClose = (value) => {
  showAnnouncement.value = value;
}
</script>