<template>
   <div class="menu-item">
      <div class="menu-item__title">{{ item.name }}</div>
      <div class="menu-item__btn" @click="handleButtonClick">Посмотреть</div>
   </div>
</template>
 
<script>
export default {
   name: 'MenuItem',
   props: {
      item: Object
   },
   methods: {
      handleButtonClick() {
         this.$emit('click1', this.item);
      }
   }
};
</script>

<style></style>