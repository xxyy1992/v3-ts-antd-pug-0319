<template lang="pug">
a-select(allow-clear placeholder="请选择1" v-if="slotName === 'operateTypeList'")
  a-select-option(v-for="it in optData.operateTypeList" :key="it" :value="it") {{it}}
a-select(allow-clear placeholder="请选择2" v-if="slotName === 'userList'")
  a-select-option(v-for="it in optData.userList" :key="it" :value="it") {{it}}
</template>

<script setup lang="ts">
// import { useAsyncState } from "@vueuse/core";
// import { SecurityLogAll } from "@/api/security";
import { reactive } from "vue";
import { any } from "vue-types";
const props = defineProps({
  slotName: {
    type: String,
    default: any,
  },
});
const optData = {
  operateTypeList: ["1", "2", "3"],
  userList: ["a", "b", "c"],
};
</script>
