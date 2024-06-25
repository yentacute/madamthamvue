<template>
  <section class="section section-margin t-contact-form">
    <div class="container">
      <div class="t-form__wrapper">
        <div class="t-form__title">
          <h2 class="h3">Liên hệ với chúng tôi</h2>
          <p class="t-form__content">Luôn sẵn sàng phục vụ bạn 24/7.</p>
        </div>
        <div class="t-form__content">
          <form action="">
            <div class="form-container">
              <div class="form-item">
                <input type="text" placeholder="Name" class="form-field" />
              </div>
              <div class="form-item">
                <input type="text" placeholder="Địa chỉ" class="form-field" />
              </div>
              <div class="form-item">
                <input type="text" placeholder="SĐT" class="form-field" />
              </div>
              <div class="form-item">
                <input type="datetime-local" placeholder="Thời gian" class="form-field" />
              </div>
              <div class="form-item">
                <input type="text" placeholder="Diện tích" class="form-field" />
              </div>
              <div class="form-item">
                <input type="text" placeholder="Mô tả chi tiết" class="form-field" />
              </div>
              <div class="form-item">
                <input type="text" placeholder="Name" class="form-field" />
              </div>

              <div class="form-item">
                <div class="form-selected">
                  <div
                    class="form-selected__title flex align-center justify-between"
                    v-if="isEmptySelected"
                    @click="handleShowSelect"
                  >
                    <span>Chọn loại phòng</span>
                    <IconDown />
                  </div>
                  <div class="form-selected__title" @click="handleShowSelect" v-else>
                    <span
                      v-for="(item, index) in selected"
                      :key="index"
                      class="form-selected__name"
                      @click="removeSelected(index)"
                    >
                      {{ item.name }}
                      <IconClose />
                    </span>
                  </div>
                </div>
                <div
                  class="form-selected__content"
                  :class="{ 'form-selected__content--show': toggleSelect }"
                >
                  <ul>
                    <li v-for="option in options" :key="option.value" @click="addTag(option)">
                      <span>{{ option.name }}</span>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
            <div class="form-item">
              <textarea
                placeholder="Ghi chú chi tiết tại đây..."
                class="form-field"
                rows="5"
              ></textarea>
            </div>
            <div class="form-item flex justify-center">
              <button type="submit">Đặt lịch</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'
import IconDown from './icons/IconDown.vue'
import IconClose from './icons/IconClose.vue'

const selected = ref([])
const toggleSelect = ref(false)
const handleShowSelect = () => {
  toggleSelect.value = !toggleSelect.value
}

const options = ref([
  { name: 'Phòng khách', value: '1' },
  { name: 'Phòng ngủ', value: '2' },
  { name: 'Nhà bếp', value: '3' }
])
const addTag = (option) => {
  const checkExisted = selected.value.some((item) => item.value === option.value)
  if (checkExisted) {
    return
  }
  selected.value.push({
    name: option.name,
    value: option.value
  })
}

const removeSelected = (index) => {
  selected.value.splice(index, 1)
}

const isEmptySelected = computed(() => selected.value.length === 0)
</script>


<style lang="scss" scoped>
@import '../assets/scss/components/contact_form.scss';
</style>

