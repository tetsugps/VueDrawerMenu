<template>
  <div id="app">
    <div>
      <button @click="openDrawerMenu">ボタン</button>
    </div>
    <transition name="right">
      <div v-if="drawerFlg" class="drawer-menu-wrapper">
        <div class="drawer-menu">めにゅー</div>
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
  background-color: skyblue;
}
.drawer-menu {
  padding: 24px;
}
</style>
