<template>
  <div id="app">
    <div>
      <button @click="openDrawerMenu" class="button">ボタン</button>
    </div>
    <transition name="right">
      <div v-if="drawerFlg" class="drawer-menu-wrapper">
        <div class="drawer-menu">Link1</div>
        <div class="drawer-menu">Link2</div>
        <div class="drawer-menu">Link3</div>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      drawerFlg: false
    };
  },
  methods: {
    openDrawerMenu() {
      this.drawerFlg = !this.drawerFlg;
    }
  }
};
</script>

<style>
.right-enter-active,
.right-leave-active {
  transform: translate(0px, 0px);
  transition: transform 225ms cubic-bezier(0, 0, 0.2, 1) 0ms;
}
.right-enter,
.right-leave-to {
  transform: translateX(100vw) translateX(0px);
}
.drawer-menu-wrapper {
  position: absolute;
  z-index: 10;
  top: 0;
  right: 0;
  width: 50%;
  height: 100%;
  background-color: black;
  color: white;
  font-size: 25px;
}
.drawer-menu {
  padding: 24px;
}
.button {
  background-color: #4CAF50; /* Green */
  border: none;
  color: white;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
}
</style>
