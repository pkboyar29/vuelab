<template>
   <div v-if="modalActive" class="modal active" @click="handleModalClick">
      <div class="modal__content" @click.stop>
         <slot>контент по умолчанию</slot>
         <slider :images="images"/>
      </div>
   </div>
   <div v-else></div>
</template>
 
<script>
import SliderItem from './SliderItem';

export default {
   name: 'ModalItem',
   props: {
      modalActive: Boolean,
      images: Array
   },
   methods: {
      handleModalClick() {
         this.$emit('close'); // генерирую пользовательское событие 
      }
   },
   components: {
   'slider': SliderItem
   }
};
</script>
 
<style></style>