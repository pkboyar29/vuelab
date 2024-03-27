<template>
   <div class="slider">
      <button @click="handlePrev">&lt;</button>
      <img :src="images[currentIndex]" :alt="`Slide ${currentIndex + 1}`" />
      <button @click="handleNext">&gt;</button>
   </div>
</template>
 
<script>
export default {
   name: 'SliderItem',
   props: {
      images: Array
   },
   data() {
      return {
         currentIndex: 0
      };
   },
   methods: {
      handlePrev() {
         this.currentIndex = this.currentIndex > 0 ? this.currentIndex - 1 : this.images.length - 1;
      },
      handleNext() {
         this.currentIndex = this.currentIndex < this.images.length - 1 ? this.currentIndex + 1 : 0;
      }
   }
};
</script>
 
<style></style>