<script setup lang="ts">
import { message } from "ant-design-vue"; //非组件模块，需手动引入后可用

const info = () => {
  message.info("This is a normal message");
};
</script>

<template>
  <div>
    <!-- 该自定义组件在src/components目录下，会自动引入 -->
    <HelloWorld :msg="'HelloWorld'" />
  </div>
</template>

<style lang="less">
@import "./assets/global.less";
</style>
