<template lang="pug">
<AntDesDemo></AntDesDemo>
a-table(:dataSource="dataSource" :columns="columns")
 template(#bodyCell="{column, record}")
  template(v-if="column.dataIndex === 'action'")
   a-button(@click="goToDetail(record.key)" type="link" size="small") 详情
<TableDetail :detailId="detailId"></TableDetail>
</template>
<script setup lang="ts">
import { ref } from "vue";
const dataSource = [
  {
    key: "1",
    name: "胡彦斌111",
    age: 32,
    address: "西湖区湖底公园1号",
  },
  {
    key: "2",
    name: "胡彦祖",
    age: 42,
    address: "西湖区湖底公园1号",
  },
];
const columns = [
  {
    title: "姓名",
    dataIndex: "name",
    key: "name",
  },
  {
    title: "年龄",
    dataIndex: "age",
    key: "age",
  },
  {
    title: "住址",
    dataIndex: "address",
    key: "address",
  },
  {
    title: "操作",
    dataIndex: "action",
    key: "action",
  },
];
let detailId = ref("");
const goToDetail = (event: any) => {
  // console.log(event);
  detailId.value = event;
  console.log(detailId.value, "detailId.value");
};
</script>
