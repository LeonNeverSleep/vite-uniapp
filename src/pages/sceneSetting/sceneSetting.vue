<template>
  <view class="scene-setting-container">
    <!-- <Header /> -->
  </view>
</template>

<script setup lang="ts">
// import Header from '@/components/Header.vue';
</script>

<style lang="scss" scoped>
.scene-setting-container {
  $paddingTop: 36.6rpx;
  $paddingLeft: 54rpx;
  padding: $paddingTop $paddingLeft;
  width: calc(100vw - $paddingLeft * 2);
  height: calc(100vh - $paddingTop * 2);
  background: linear-gradient(
    168deg,
    #66b6f8 1%,
    #daeaf9 37%,
    #f4e9f2 63%,
    #f7fcff 100%,
    #dfecfc 100%
  );
  opacity: 1;
}
</style>
