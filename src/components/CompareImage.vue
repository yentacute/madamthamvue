<template>
  <section class="t-compare section"
    :style="buttonStyle"> 
    <div class="container">
      <div class="t-compare__container"  ref="compareEl" >
      <div class="t-compare__before t-compare--media">
      <p class="t-compare__heading h6">Before</p>
      <div class="t-compare__image-wrapper">
        <img src="../assets/images/slider/4.jpg" alt="" />
      </div>
    </div>
    <div class="t-compare__after t-compare--media">
      <p class="t-compare__heading h6">After</p>
      <div class="t-compare__image-wrapper">
        <img src="../assets/images/slider/5.jpg" alt="" />
      </div>
    </div>

    <div class="t-compare__button" aria-label="Drag" 
    
      @mousedown="handleCompareStart">
      <span
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          aria-hidden="true"
          focusable="false"
          fill="none"
          viewBox="0 0 11 16"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M0 0.5C0 0.223858 0.223858 0 0.5 0C0.776142 0 1 0.223858 1 0.5V15.5C1 15.7761 0.776142 16 0.5 16C0.223858 16 0 15.7761 0 15.5V0.5ZM5 0.5C5 0.223858 5.22386 0 5.5 0C5.77614 0 6 0.223858 6 0.5V15.5C6 15.7761 5.77614 16 5.5 16C5.22386 16 5 15.7761 5 15.5V0.5ZM11 0.5C11 0.223858 10.7761 0 10.5 0C10.2239 0 10 0.223858 10 0.5V15.5C10 15.7761 10.2239 16 10.5 16C10.7761 16 11 15.7761 11 15.5V0.5Z"
            fill="currentColor"
          ></path></svg
      ></span>
    </div>
      </div>
    </div>

  </section>
</template>

<script setup>
  import { ref, computed } from "vue";
  const percentage = ref(50);
  let isDragging = false;
  const compareEl = ref(null);

  // Define a computed property for the style
  const buttonStyle = computed(() => ({
    '--percentage': `${percentage.value}%`
  }));

  const handleCompareStart = (event) => {
    console.log(event, 'start');
    isDragging = true;
    document.addEventListener('mousemove', handleCompareMove);
    document.addEventListener('mouseup', handleCompareEnd);

  }

  const handleCompareEnd = (event) => {
    console.log(event, 'end');
    isDragging = false;
    document.removeEventListener('mousemove', handleCompareMove);
    document.removeEventListener('mouseup', handleCompareEnd);
  }

  const handleCompareMove = (event) => {
     if (!isDragging) return;
    // const tCompareEl = event.target.closest('.t-compare');
    // console.log(tCompareEl, 'compareEl');
    const rect = compareEl.value.getBoundingClientRect();
    const offsetX = event.clientX - rect.left; // Get mouse X position relative to the container
    const width = rect.width;
    // Calculate percentage and update
    const newPercentage = Math.min(100, Math.max(0, (offsetX / width) * 100));
    percentage.value = newPercentage;

  }

  document.addEventListener('scroll', (event) => {
    console.log('event');
  });
</script>

<style lang="scss" scoped>
@import '../assets/scss/components/compare.scss';
</style>