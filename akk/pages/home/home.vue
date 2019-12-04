<template>
	<view>
		<!--+++++++++++++++++ header ++++++++++++++++++-->
		<view class="home-header">
			<image src="" mode=""></image>
			金岛企业咨询
			新疆维吾尔族XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXxx
			XXXXXXXXXXXXxx
			<image src="" mode=""></image>
		</view>
		<!-- +++++++++++++++++++++++++++++++++++banner-part+++++++++++++++++++++++++++++++++++++++++++ -->
		<view class="banner-part">
			<image src="" mode=""></image>
		</view>
		<!--++++++++++++++++++++++++++++++++++++++++++ cargo-part+++++++++++++++++++++++++++++++++++++++++++= -->
		<view class="cargo-part">
			<image src="" mode=""></image>
			<text>爱豆豆：个</text>
			<text>￥</text>
			<text>￥</text>
			<image src="" mode=""></image>
		</view>
		<!--+++++++++++++++++++++++++  商品列表  ————++++++++++++++++++++++-->
		<uni-load-more :status="loadingType"></uni-load-more>
	</view>
</template>

<script>
	import uniLoadMore from "@/components/uni-load-more/uni-load-more.vue"
	export default {
		components: {uniLoadMore},
		data() {
			return {
				loadingType: 'more', //加载更多状态
			};
		},
		 onPullDownRefresh() {
		        console.log('已刷新');
		        setTimeout(function () {
		            uni.stopPullDownRefresh();
		        }, 1000);
		    },
		onReachBottom(){
				console.log('已加载');
				
			},
		
	}
</script>

<style lang="scss">

</style>
