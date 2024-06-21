<template>
  <div class="t-wrapper">
    <HeaderComponent/>
    <main>
        <slot></slot>
    </main>
    <Footer/>

  </div>
</template>

<script setup>
  import HeaderComponent from './HeaderLayout.vue';
  import Footer from './FooterLayout.vue';

</script>

<style lang="scss" scoped>

</style>