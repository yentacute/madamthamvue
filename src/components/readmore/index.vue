<template>
  <div class="section t-information">
    <div class="container">
      <div class="t-information__wrapper"
        :class="props.classes"
      >
        <div class="t-information__img w-60">
          <slot name="img"></slot>
        </div>
        <div class="t-information__content w-40">
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
      default: 't-flex align-center'
    }
  })
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