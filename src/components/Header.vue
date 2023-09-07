<template>
  <view class="header-container flex">
    <Crumb :data-list="crumbList" />
    <SettingBtn />
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import Crumb from '@/components/Crumb.vue';
import SettingBtn from '@/components/SettingBtn.vue';

const crumbList = ref(['福州大学智能控制面板', 'IFC-903', '场景编辑']);
</script>

<style lang="scss" scoped>
.header-container {
}
</style>
