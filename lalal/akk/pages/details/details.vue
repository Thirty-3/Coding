<template>
	<view>
		<!-- banner -->
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
		<!-- 名称、评价等 -->
		<view class="header">
			<text>测试商品</text>
			<br />
			<text>￥222</text>  <text>￥555</text>  <text>爱豆豆:0个</text>
			<br />
			<text>会员价300</text>  <text>快递：免运费</text>
			<view class="evaluate">
				<text>评价（0）</text>
				<uni-rate :disabled="true" :value="3.5" />
				<text>全部评价</text>
				<image src="" mode=""></image>
			</view>
			<view class="add-cart">
				加入购物车
			</view>
		</view>
		<!-- 领券 -->
		<view class="coupon" @tap="">
			<text>领券</text>  <text>优惠券</text>  <text>暂无优惠券</text>
		</view>
		<!-- 商品详情 -->
		<uni-list>
			<uni-list-item title="" note="" @tap="">商品详情</uni-list-item>
			<uni-list-item title="" note="" @tap="">产品信息</uni-list-item>
		</uni-list>
		<!-- 去结算 -->
		<view class="">
			<image src="" mode=""></image>
			<text>￥goodsVipAmount</text> <text>已减1000元</text>
			<view class="cart-right" @tap="$Router.push({name:'settlement'})">
				去结算
			</view>
		</view>
	</view>
</template>

<script>
	import uniRate from '@/components/uni-rate/uni-rate.vue'
	export default {
		components: {
			uniRate,
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">

</style>
