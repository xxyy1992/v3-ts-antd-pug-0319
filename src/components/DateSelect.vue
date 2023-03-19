<template lang="pug">
a-range-picker(:show-time="{defaultValue: [dayjs('00:00:00', 'HH:mm:ss'), dayjs('00:00:00', 'HH:mm:ss')]}" allowClear valueFormat="YYYY-MM-DD HH:mm:ss" v-bind="$attrs" @change="handleChange")
</template>

<script setup lang="ts">
import { ref, watch } from "vue";
import dayjs from "dayjs";
import type { Dayjs } from "dayjs";
const props = withDefaults(
  defineProps<{
    paramKey?: string[];
  }>(),
  {
    paramKey: () => ["syncStartTime", "syncEndTime"],
  }
);
const handleChange = (value: [Dayjs, Dayjs]) => {
  let keys = [`params.${props.paramKey[0]}`, `params.${props.paramKey[1]}`];
  let params: Record<string, any> = {};
  params[keys[0]] = value ? value[0] : "";
  params[keys[1]] = value ? value[1] : "";
};
</script>
