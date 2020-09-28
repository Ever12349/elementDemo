<template>
  <el-drawer
    ref="elDrawer"
    :wrapperClosable="true"
    :visible.sync="drawer"
    direction="rtl"
    :append-to-body="true"
    :before-close="handleClose"
    :with-header="false"
    :destroyOnClose="true"
    :size="drawerSize"
    :modal="false"
    @open="drawerOpen"
    @close="drawerClose"
  >
    <div class="drawer-body">
      <slot v-if="drawer"></slot>
    </div>
  </el-drawer>
</template>
<script>
export default {
  name: "drawer",
  props: {
    drawerTitle: {
      type: String,
      default: "我是标题",
    },
    headerType: {
      type: String,
      default: "normal",
    },
    drawerSize: {
      type: String,
      default: "900px",
    },
    isShowHit: {
      type: [String, Boolean, Number],
      default: true,
    },
  },
  data() {
    return {
      drawer: false,
      test: "1",
    };
  },
  mounted() {
    console.log(this.isShowHit, "isShowHit");
  },
  methods: {
    drawerOpen() {
      this.$emit("drawerOpen");
    },
    drawerClose() {
      this.$emit("drawerClose");
    },
    handleClose() {
      this.drawer = false;
    },
    openDrawer() {
      this.drawer = true;
    },
    closeDrawer() {
      this.$refs.elDrawer.closeDrawer();
    },
  },
};
</script>
<style lang="scss" scoped>
$drawer-header-height: 70px;
.drawer-body {
  width: 100%;
  height: calc(100% - #{$drawer-header-height});
}
</style>