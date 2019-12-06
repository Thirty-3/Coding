<template>
    <view>
        <view class="uni-padding-wrap">
            <view class="page-section swiper">
                <view class="page-section-spacing">
                    <swiper class="swiper" :indicator-dots="true" :autoplay="true" :interval="2000" :duration="500" :circular="true">
                        <swiper-item>
                            <view class="swiper-item uni-bg-red">A</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-green">B</view>
                        </swiper-item>
                        <swiper-item>
                            <view class="swiper-item uni-bg-blue">C</view>
                        </swiper-item>
                    </swiper>
                </view>
            </view>
        </view>
    </view>
</template>
<script>
export default {
    data() {
        return {

        }
    }
	}
</script>

<style lang="scss">

</style>
