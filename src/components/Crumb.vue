<template>
  <view class="crumb-container">
    <ul class="flex-start">
      <template v-for="(item, index) of props.dataList">
        <li class="li-style">{{ item }}</li>
        <span v-show="index < props.dataList.length - 1"> &gt; </span>
      </template>
    </ul>
  </view>
</template>

<script setup lang="ts">
export interface Props {
  dataList: string[];
}

const props = withDefaults(defineProps<Props>(), {
  dataList: () => ['福州大学智能控制面板', 'IFC-903', '场景编辑'],
});
</script>

<style lang="scss" scoped>
.crumb-container {
  font-size: 12.6rpx;
  font-family: PingFang SC-Medium, PingFang SC;
  font-weight: 400;
  color: #666666;

  .li-style {
    margin: 0 6rpx;
  }
}
</style>
