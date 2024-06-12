<template>
  <div class="t-wrapper">
    <HeaderComponent/>
    <main>
        <slot></slot>
    </main>
    <FooterComponent/>

  </div>
</template>

<script setup>
  import HeaderComponent from '../layout/header.vue'
  import FooterComponent from '../layout/footer.vue'

</script>

<style lang="scss" scoped>

</style>