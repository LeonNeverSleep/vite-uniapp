<template>
  <view class="background-selector-container">
    <ul class="flex-start">
      <li v-for="(item, index) in props.listData" :key="index">
        <!-- {{ item.url }} -->
        <image :src="item.url" alt="" srcset="" />
      </li>
    </ul>
  </view>
</template>

<script setup lang="ts">
import img_1 from '@/assets/images/img_1.png';

export interface ImageType {
  url: string;
}

export interface VideoType extends ImageType {
  url: string;
  videoUrl: string;
}

export interface Props {
  listData: ImageType[] | VideoType[];
}

const props = withDefaults(defineProps<Props>(), {
  listData: () => [
    {
      url: img_1,
    },
    {
      url: img_1,
    },
    {
      url: img_1,
    },
    {
      url: img_1,
    },
  ],
});
</script>

<style lang="scss" scoped>
.background-selector-container {
  ul {
    li {
      $size: 72rpx;
      margin-right: 24rpx;
      width: $size;
      height: $size;
      border-radius: 3rpx;
      opacity: 1;
      border: 1rpx solid #000000;
      overflow: hidden;
      &:nth-last-child(1) {
        margin: 0;
      }
      image {
        width: 100%;
        height: 100%;
      }
    }
  }
}
</style>
