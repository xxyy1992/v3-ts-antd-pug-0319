<template lang="pug">
//- .container#containerheader.header 
//-  h1.title {{ title }}:{{ content }}
//-  footer.footer 
//-    a-button 确定 
//-    a-button.cancel 取消
//- <DateSelect :paramKey="[]"></DateSelect>
//- h2.title 选择框1<InputSelect :slotName="'operateTypeList'"></InputSelect>
//- h3.title 选择框2<InputSelect :slotName="'userList'"></InputSelect>
<TableList></TableList>
</template>
<script setup lang="ts">
import { ref } from "vue";

defineProps<{ msg: string }>();

const content = ref("欢迎使用pug");
const title = ref("标题");
</script>

<style scoped></style>
