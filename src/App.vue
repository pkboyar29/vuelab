<template>
  <div class="container">
    <menu-container />
  </div>
</template>

<script>
import MenuContainer from './components/MenuContainer';

export default {
  name: 'App',
  components: {
    'menu-container': MenuContainer
  }
}
</script>

<style>
.container {
  max-width: 1230px;
  margin: 0 auto;
}

.menu {
  margin-top: 45px;
  display: flex;
  flex-wrap: wrap;
  gap: 30px;
}

.menu-item {
  margin-bottom: 10px;
  text-align: center;
}

.menu-item__title {
  font-size: 18px;
  font-weight: 700;
  margin-bottom: 5px;
}

.menu-item__btn {
  cursor: pointer;
  padding: 3px;
  border: 1px solid #000;
  border-radius: 4px;
  color: #000;
  transition: all 0.3s;
}

.menu-item__btn:hover {
  color: #fff;
  background-color: #000;
}

.modal {
  height: 100vh;
  width: 100vw;
  background-color: rgba(0, 0, 0, 0.4);
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  opacity: 0;
  pointer-events: none;
  transition: 0.5s;
}

.modal.active {
  opacity: 1;
  pointer-events: all;
}

.modal__content {
  padding: 20px;
  border-radius: 12px;
  background-color: #fff;
  text-align: center;
}
</style>
