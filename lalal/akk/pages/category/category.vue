<template>
	<view class="all">
		<view class="search-part">
			
		</view>
		<uni-list class="type-list">
			<uni-list-item title="全部" @tap="$Router.push({name:'list'})" class="list"/>
		</uni-list>
		<uni-list class="type-list">
			<uni-list-item title="全部" @tap="$Router.push({name:'list'})" class="list"/>
		</uni-list>
		<uni-list class="type-list">
			<uni-list-item title="全部" @tap="$Router.push({name:'list'})" class="list"/>
		</uni-list>
		<uni-list class="type-list">
			<uni-list-item title="全部" @tap="$Router.push({name:'list'})" class="list"/>
		</uni-list>
	</view>
</template>

<script>
	import uniList from '@/components/uni-list/uni-list.vue'
	import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
	export default {
		components: {
			uniList,
			uniListItem
		},
		data() {
			return {
				
			}
		},

	}
</script>

<style lang="scss">
	.all{
		background: #f2f3f7;
		width: 100%;
		height: 1300upx;
		>.search-part{
			width: 100%;
			height: 80upx;
			background: #f40;
		}
		>.type-list{
			width: 90%;
			margin-left: 5%;
			background-color: #fff;
			position: relative;
			margin-top: 28upx;
}
	}

.popup-bottom{
	border-radius: 5%;
	height: 600upx;
	background: #FFFFFF;
	>.close{
		width: 100%;
		height: 70upx;
		>text{
			float: right;
			margin-right: 30upx;
		}
	}
	>.goods-detail{
		width: 690upx;
		height: 200upx;
		margin: 0 auto;
		>.detail-left{
			float: left;
			width: 180upx;
			height: 180upx;
			>image{
				width: 180upx;
				height: 180upx;
			}
		}
		>.detail-right{
			float: right;
			width: 480upx;
			height: 180upx;
			>.ming-cheng{
				font-size: 28upx;
			}
			>.jia-ge{
				line-height: 60upx;
				color: rgb(255, 68, 68);
				font-size: 32upx;
			}
			>.dan-wei{
				font-size: 12px;
				color: #bebebe;
				line-height: 60upx;
			}
			>.detail-aidoudou{
				margin-left: 20upx;
			    font-size: 12px;
			    color: #bebebe;
				line-height: 60upx;
			}
			>.ku-cun{
				font-size: 13px;
			}
		}
	}
	.specs{
		overflow: hidden;
		padding: 20upx 0;
		width: 100%;
		height: 40upx;
		>text{
			color: #333;
			font-size: 28upx;
			margin-right: 20upx;
			float: left;
		}
		>button{
			float: left;
			height: 40upx;
			width: 56upx;
			outline: none;
			border: 2upx solid #c7c7c7;
			color: #c7c7c7;
			font-size: 24upx;
			line-height: 24upx;
			background-color: #fff;
			margin-right: 20upx;
			padding: 4upx 8upx;
		}
	}
	.number{
		// overflow: hidden;
		// padding: 20upx 0;
		width: 100%;
		height: 60upx;
		display: flex;
		justify-content: space-between;
		>text{
			font-size: 36upx;
			line-height: 60upx;
		}
		>.number-box{
			width: 130upx;
		}
	}
	.zong-jia{
		margin-top: 20upx;
		width: 100%;
		height: 60upx;
		display: flex;
		justify-content: space-between;
	}
	.add-cart{
			width: 750upx;
			height: 100upx;
			font-size: 32upx;
			line-height: 100upx;
			text-align: center;
			color: #fff;
			background-color: #ff976a;
			z-index: 999;
			position: absolute;
			top: 500rpx;
			left: 0;
	}
}
</style>
