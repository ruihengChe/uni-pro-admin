<template>
    <view class="content">
        <image class="logo" src="/static/logo.png" />
        <view class="text-area">
            <text class="title">{{ title }}</text>
            <button @click="toAbout">去首页</button>
        </view>
    </view>
</template>

<script setup lang="ts">
import { ref, getCurrentInstance } from 'vue'
const title = ref('去首页')
const toAbout = () => {
    uni.navigateTo({
        url: '/pages/index/index'
    })
}
onLoad(() => {
    // 通讯获取事件
    const instance = getCurrentInstance()?.proxy
    // @ts-expect-error-error
    const eventChannel = instance.getOpenerEventChannel()
})
</script>

<style>
.content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
}

.logo {
    height: 200rpx;
    width: 200rpx;
    margin-top: 200rpx;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 50rpx;
}

.text-area {
    display: flex;
    justify-content: center;
}

.title {
    font-size: 36rpx;
    color: #8f8f94;
}
</style>
