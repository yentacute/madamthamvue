<template>
  <section class="section t-contact-form">
    <div class="container">
      <div class="t-form__wrapper">
        <form action="">
          <div class="t-form__item">
            <label for="name">Name</label>
            <input type="text" placeholder="Name" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="address">Địa chỉ</label>
            <input type="text" placeholder="Địa chỉ" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="phone">SĐT</label>
            <input type="text" placeholder="SĐT" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="rooms">Số lượng</label>
            <input type="text" placeholder="Số lượng" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="square">Diện tích</label>
            <input type="text" placeholder="Diện tích" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="details">Mô tả chi tiết</label>
            <input type="text" placeholder="Mô tả chi tiết" class="t-input">
          </div>
          <div class="t-form__item">
            <label for="name">Name</label>
            <input type="text" placeholder="Name" class="t-input">
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
  import { ref } from 'vue'
import Multiselect from 'vue-multiselect'

  const options = ref([
    { id: 1, name: 'Option 1' },
    { id: 2, name: 'Option 2' },
    { id: 3, name: 'Option 3' },
    { id: 4, name: 'Option 4' },
    { id: 5, name: 'Option 5' },
    { id: 6, name: 'Option 6' },
    { id: 7, name: 'Option 7' },
    { id: 8, name: 'Option 8' },
    { id: 9, name: 'Option 9' },
    { id: 10, name: 'Option 10' },
    { id: 11, name: 'Option 11' },
    { id: 12, name: 'Option 12' }
  ])

</script>

<style lang="scss" scoped>

</style>