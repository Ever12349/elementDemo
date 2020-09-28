<template>
  <el-form size="small" label-position="top">
    <el-row class="container" :gutter="30">
      <el-col :span="8">
        <el-form-item :rules="[{ required: true }]" label="港口代码">
          <el-select style="width: 100%" filterable clearable v-model="form.a">
            <el-option
              v-for="item in options"
              :key="item.value"
              :label="item.label"
              :value="item.value"
            >
            </el-option>
          </el-select>
        </el-form-item>
      </el-col>
      <el-col :span="8">
        <el-form-item :rules="[{ required: true }]" label="港口代码">
          <el-input v-model="form.b" placeholder="请输入港口代码"></el-input>
        </el-form-item>
      </el-col>
      <el-col :span="8">
        <el-form-item :rules="[{ required: true }]" label="港口代码">
          <el-input v-model="form.c" placeholder="请输入港口代码"></el-input>
        </el-form-item>
      </el-col>
    </el-row>
  </el-form>
</template>
<script>
export default {
  name: "drawerInner",
  data() {
    return {
      form: { a: "", b: "", c: "" },
      options: [],
    };
  },
  created() {},
  mounted() {
    setTimeout(() => {
      this.options = [
        {
          value: "选项1",
          label: "黄金糕",
        },
        {
          value: "选项2",
          label: "双皮奶",
        },
        {
          value: "选项3",
          label: "蚵仔煎",
        },
        {
          value: "选项4",
          label: "龙须面",
        },
        {
          value: "选项5",
          label: "北京烤鸭",
        },
      ];
    }, 200);
  },
};
</script>
<style lang="scss" scoped>
.container {
  padding: {
    left: 20px;
    right: 10px;
  }
}
</style>