<template>
   <div class="menu">
      <menu-item v-for="item in jsonData" :key="item.id" :item="item" @click1="handleMenuItemClick" />
   </div>
   <modal :modalActive="modalActive" :images="selectedItemImages" @close="handleModalClose">
      <p>{{ selectedItem && selectedItem.name }}</p>
      <p>Дополнительное содержимое</p>
   </modal>
</template>

<script>
import MenuItem from './MenuItem';
import ModalItem from './ModalItem';
import jsonData from '../data.json';

export default {
   name: "MenuContainer",
   data() {
      return {
         jsonData: jsonData,
         modalActive: false,
         selectedItem: null
      }
   },
   components: {
      'menu-item': MenuItem,
      'modal': ModalItem
   },
   computed: {
      selectedItemImages() {
         // Проверяем, есть ли selectedItem и свойства src1, src2, src3, src4
         return this.selectedItem && [this.selectedItem.src1, this.selectedItem.src2, this.selectedItem.src3, this.selectedItem.src4]
      }
   },
   methods: {
      handleMenuItemClick(item) {
         console.log('привет')
         this.modalActive = true;
         this.selectedItem = item;
      },
      handleModalClose() {
         this.modalActive = false;
         // сделать selectedItem null?
         this.selectedItem = null
      }
   }
};
</script>

<style></style>