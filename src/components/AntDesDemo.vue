<template lang="pug">
a-radio-group(v-model:value="size")
 a-radio-button(value="large") 大号
 a-radio-button(value="default") 中号
 a-radio-button(value="small") 小号
br
br
a-space
 a-button(type="primary" :size="size") 按钮1
 a-button(type="text" :size="size") 按钮2
 a-button(type="dashed" :size="size") 按钮3
 a-button(danger :size="size") 按钮4
br
br
a-button(type="primary" :size="size")
 template(#icon)
  DownloadOutlined
a-button(type="primary" shape="circle" :size="size")
 template(#icon)
  DownloadOutlined
a-button(type="primary" shape="round" :size="size")
 template(#icon)
  DownloadOutlined
a-button(type="primary" :size="size") 下载
 template(#icon)
  DownloadOutlined
a-button(type="primary" shape="round" :size="size") 下载
  template(#icon)
   DownloadOutlined
br
br
a-breadcrumb
 a-breadcrumb-item Home
 a-breadcrumb-item
  a(target="_blank" rel="noopener noreferrer" href="") General
  template(#overlay)
   a-menu
    a-menu-item
      a(target="_blank" rel="noopener noreferrer" href="") TTTT
    a-menu-item
      a(target="_blank" rel="noopener noreferrer" href="") PPPP
 a-breadcrumb-item Button
br
br
a-dropdown-button(@click="clickButton()") Dropdown
 template(#overlay)
  a-menu(@click="clickMenu()")
    a-menu-item(key="1") 下拉1
     UserOutlined
    a-menu-item(key="2") 下拉2
    a-menu-item(key="3") 下拉3
</template>
<script setup lang="ts">
import { SizeType } from "ant-design-vue/lib/config-provider";
import { ref } from "vue";
const size = ref<SizeType>("large");
const clickButton = () => {};
const clickMenu = () => {};
</script>
