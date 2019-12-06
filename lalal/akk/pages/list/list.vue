<template>
	<view class="content">
		<view search-part>
			<uni-search-bar radius="100" placeholder="请输入内容"  />
		</view>
		
		
		<waterfall :list='list' :space='16' :column='2'>
		</waterfall>
	</view>
</template>

<script>
  import waterfall from '@/components/kcy-waterfall/waterfall'
  import dataList from '@/static/kcy-waterfall/data.json'
  import uniLoadMore from "@/components/uni-load-more/uni-load-more.vue"
  import uniSearchBar from '@/components/uni-search-bar/uni-search-bar.vue'
	export default {
    components: {
      waterfall,
	  uniLoadMore,
	  uniSearchBar
    },
		data() {
			return {
				list: [],
				loadingType: 'more'
			}
		},
		onLoad() {
      setTimeout(() => {
        this.list = dataList
      }, 20)
      
		},
		methods: {
			
		},
		onPullDownRefresh() {
		        console.log('已刷新');
		        setTimeout(function () {
		            uni.stopPullDownRefresh();
		        }, 1000);
		    },
		onReachBottom(){
				console.log('已加载');
		}
	}
	
</script>

<style>
	.content {
		text-align: center;
		height: 400upx;
	}

	.logo {
		height: 200upx;
		width: 200upx;
		margin-top: 200upx;
	}

	.title {
		font-size: 36upx;
		color: #8f8f94;
	}
</style>
