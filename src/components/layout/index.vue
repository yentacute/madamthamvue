<template>
  <div class="t-wrapper">
    <HeaderLayout/>
    <main>
        <slot></slot>
    </main>
    <FooterLayout/>

  </div>
</template>

<script setup>
  import HeaderLayout from './HeaderLayout.vue';
  import FooterLayout from './FooterLayout.vue';

</script>

<style lang="scss" scoped>

</style>