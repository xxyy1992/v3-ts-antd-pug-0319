<template lang="pug">
a-card(:title="titleName").spanleft
 template(#extra)
  a-button(@click="openDialog()") 审核归档
  a-modal(v-model:visible="visible" title="审核归档" :maskClosable="false" :closable="false" ok-text="确认" cancel-text="取消" @ok="handleOk")
   a-textarea(v-model:value="value2" placeholder="输入评论" :bordered="false")
a-card(title="操作详情").spanleft
  a-row
    a-col(:span="8").spanleft 操作人：{{ dataInfo.name }}
    a-col(:span="8").spanleft 操作类型：{{ dataInfo.type }}
    a-col(:span="8").spanleft 功能模块：{{ dataInfo.modeltype }}
    a-col(:span="8").spanleft 操作时间：{{ dataInfo.time }}
    a-col(:span="8").spanleft 操作客户端：{{ dataInfo.typemodel }}
    a-col(:span="8").spanleft 操作系统：{{ dataInfo.typext }}
    a-col(:span="8").spanleft 浏览器：{{ dataInfo.llq }}
    a-col(:span="8").spanleft IP地址：{{ dataInfo.ipaddr }}
br
br
a-card(title="请求详情").spanleft
  a-row
    a-col(:span="8").spanleft 接口地址：{{ dataInfo.name }}
    a-col(:span="8").spanleft 请求类型：{{ dataInfo.type }}
  a-descriptions(title="请求详情：" layout="vertical" bordered="false")
   a-descriptions-item CDPOIHDS
    
</template>
<script setup lang="ts">
import { reactive, ref } from "vue";
import { any } from "vue-types";
const props = defineProps({
  detailId: {
    type: String,
    default: any,
  },
});
let titleName = "安全日志详情" + props.detailId;
console.log(titleName, "detailId");
const dataInfo = reactive({
  name: "123",
  type: "用户登陆登出",
  modeltype: "试验车管理平台",
  time: "2023-0203-2023-0403",
  typemodel: "MAC",
  typext: "Mac OS",
  llq: "Chorme",
  ipaddr: "127.0.0.1",
});
const visible = ref<boolean>(false);
const value2 = ref("");
const openDialog = () => {
  visible.value = true;
};
const handleOk = (e: MouseEvent) => {
  console.log(e, "123");
  visible.value = false;
};
</script>
<style scoped>
.spanleft {
  text-align: left;
}
</style>
