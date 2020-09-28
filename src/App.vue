<template>
  <div id="app">
    <el-button @click="openDrawer">打开抽屉</el-button>
    <drawer ref="drawer" drawerSize="1200px">
      <drawer-inner></drawer-inner>
    </drawer>
  </div>
</template>

<script>
export default {
  name: "App",
  components: {
    // HelloWorld
    drawerInner: () => import("./components/drawerInner"),
    drawer: () => import("./components/drawer"),
  },
  data() {
    return {
      drawer: false,
    };
  },
  methods: {
    openDrawer() {
      // this.drawer = true;
      this.$refs.drawer.openDrawer();
    },
    handleClose() {
      this.drawer = false;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
