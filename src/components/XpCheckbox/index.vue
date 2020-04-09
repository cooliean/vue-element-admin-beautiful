<template>
  <el-checkbox :class="theme" v-model="value1" @change="change">
    <slot></slot>
  </el-checkbox>
</template>

<script>
export default {
  name: "XpCheckbox",
  props: {
    value: {
      type: Boolean,
      default: false,
    },
    theme: {
      type: String,
      default: "theme1",
    },
  },
  data() {
    return {
      value1: this.value,
    };
  },
  methods: {
    change(val) {
      this.$emit("input", val);
    },
  },
};
</script>

<style lang="scss">
.theme1 {
  .el-checkbox__inner {
  }
}
.theme2 {
  .el-checkbox__inner {
    border-radius: 99px;
  }
}
.theme3 {
  .el-checkbox__input.is-checked .el-checkbox__inner {
    background-color: #00cd00;
    border-color: #00cd00;
  }
  .el-checkbox__input.is-checked + .el-checkbox__label {
    color: #00cd00;
  }
}
</style>
