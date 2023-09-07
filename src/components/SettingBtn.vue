<template>
  <view class="setting-btn-container">
    <view @click="open('center')">设置</view>
    <uni-popup
      class="popup-style"
      ref="popupRef"
      background-color="#fff"
      @change="changePopup"
    >
      <view class="popup-container">
        <view class="header-style">
          <view>设置</view>
          <view class="close-btn-style">X</view>
        </view>

        <view class="form-style">
          <view class="label-style">选择控制区域</view>
          <ul class="area-box-style flex-start">
            <li class="area-item-style">
              <uni-data-select
                v-model="areaRef.campus"
                :localdata="areaListDataRef.campus"
                @change="changeArea"
              ></uni-data-select>
            </li>
            <li class="area-item-style">
              <uni-data-select
                v-model="areaRef.building"
                :localdata="areaListDataRef.building"
                @change="changeArea"
              ></uni-data-select>
            </li>
            <li class="area-item-style">
              <uni-data-select
                v-model="areaRef.floor"
                :localdata="areaListDataRef.floor"
                @change="changeArea"
              ></uni-data-select>
            </li>
          </ul>
          <view class="label-style">图片</view>
          <BackgroundSelector />
          <view class="label-style">视频</view>
          <BackgroundSelector />
        </view>
      </view>
    </uni-popup>
  </view>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import BackgroundSelector from '@/components/BackgroundSelector.vue';

// 弹出层对象
const popupRef = ref();

/**
 * 改变弹出层状态
 * @param e 传输事件对象
 */
const changePopup = (e: { type: string; show: string }) => {
  console.log('当前模式：' + e.type + ',状态：' + e.show);
};

/**
 * 显示弹出层
 * @param positon 弹出层位置
 */
const open = (positon: string) => {
  console.log('pupupRef :>> ', popupRef.value.open(positon));
};

// 区域数据
const areaRef = ref({
  campus: '',
  building: '',
  floor: '',
});

// 区域选项数据
const areaListDataRef = ref({
  campus: [
    { value: 0, text: '福大校区' },
    { value: 1, text: 'IFC' },
  ],
  building: [
    { value: 0, text: '科研楼' },
    { value: 1, text: '宿舍楼' },
  ],
  floor: [
    { value: 0, text: '1F' },
    { value: 1, text: '2F' },
  ],
});

const changeArea = () => {};
</script>

<style lang="scss" scoped>
.setting-btn-container {
  .popup-style {
    :deep(.uni-popup__wrapper) {
      border-radius: 9rpx;
    }

    .popup-container {
      padding: 22.5px 30rpx;
      width: 420rpx;
      height: 420rpx;
      overflow: hidden;

      .header-style {
        text-align: center;
        font-size: 12.6rpx;
        font-weight: bold;
        font-family: PingFang SC-Bold, PingFang SC;
        color: #3d3d3d;
        position: relative;

        .close-btn-style {
          position: absolute;
          top: 0;
          right: 0;
        }
      }

      .form-style {
        margin-top: 20.7rpx;
        .label-style {
          margin: 12rpx 0 9.6rpx 0;
          font-size: 13rpx;
          font-family: PingFang SC-Medium, PingFang SC;
          font-weight: 400;
          color: #9e9e9e;
        }
        .area-box-style {
          .area-item-style {
            margin-right: 4.5rpx;
            width: 117rpx;
            height: 31.2rpx;
            :v-deep(.uni-stat__select) {
              width: 100%;
              height: 100%;
              .uni-stat-box {
                width: 100%;
                height: 100%;
                .uni-select {
                  width: 100%;
                  height: 100%;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
