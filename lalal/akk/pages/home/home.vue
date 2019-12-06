<template>
	<view>
		<!-- header -->
		<view class="home-header">
			<image src="../../static/img/home/4.png" mode=""></image>
				<view class="title">
				<text class="business-firm">金岛企业咨询</text><br />
				<text class="address">新疆维吾尔自治区阿克苏地区阿克苏市撒哈拉沙漠</text>
				</view>
			<image src="../../static/img/home/-e-yyz@2x.png" mode=""></image>
		</view>
		<!-- banner-part -->
		<view class="banner-part">
			<view class="left-img">
				<image src="../../static/img/home/1.jpg" mode="" ></image>
			</view>
			<view class="right-img">
				<image src="../../static/img/home/2.jpg" mode=""></image>
				<image src="../../static/img/home/3.jpg" mode=""></image>
			</view>
		</view>
		<!-- cargo-part -->
		<view class="cargo-part">
			<view class="goods">
				<uni-card :is-shadow="true">
					
					<view class="goods-left">
						<image src="../../static/img/home/1.png" mode=""></image>
					</view>
					
					<view  @click="open" class="add">
						<image src="../../static/img/home/add.png" mode=""></image>
					</view>
					
					<view class="goods-right">
						<text class="goods-name">测试商品</text>
						<br />
						<text class="aidoudou">爱豆豆：10个</text>
						<br />
						<text class="price">￥100</text>
						<text class="original-price">￥15</text>
					</view>
					
				</uni-card>
			</view>
			<view class="goods">
				<uni-card :is-shadow="true">
					
					<view class="goods-left">
						<image src="../../static/img/home/1.png" mode=""></image>
					</view>
					
					<view  @click="open" class="add">
						<image src="../../static/img/home/add.png" mode=""></image>
					</view>
					
					<view class="goods-right">
						<text class="goods-name">测试商品</text>
						<br />
						<text class="aidoudou">爱豆豆：10个</text>
						<br />
						<text class="price">￥100</text>
						<text class="original-price">￥15</text>
					</view>
					
				</uni-card>
			</view>
			<view class="goods">
				<uni-card :is-shadow="true">
					
					<view class="goods-left">
						<image src="../../static/img/home/1.png" mode=""></image>
					</view>
					
					<view  @click="open" class="add">
						<image src="../../static/img/home/add.png" mode=""></image>
					</view>
					
					<view class="goods-right">
						<text class="goods-name">测试商品</text>
						<br />
						<text class="aidoudou">爱豆豆：10个</text>
						<br />
						<text class="price">￥100</text>
						<text class="original-price">￥15</text>
					</view>
					
				</uni-card>
			</view>
		</view>
		<!--  商品列表  -->
		<uni-load-more :status="loadingType"></uni-load-more>
		<!-- 下弹窗 -->
		<view>
			<uni-popup :show="false" type="bottom" ref="popup"   @hidePopup="hidePopup">
				<view class="popup-bottom">
					
					<view class="close" @tap="close">
						<text>x</text>
					</view>
					<view class="goods-detail">
						<view class="detail-left">
							<image src="../../static/img/home/1.png" mode=""></image>
						</view>
						<view class="detail-right">
							<text class="ming-cheng">
								测试商品
							</text>
							<br />
							<text class="jia-ge">
								￥500
							</text>
							<text class="dan-wei">
								/份
							</text>
							<text class="detail-aidoudou">
								爱豆豆:0
							</text>
							<br />
							<text class="ku-cun">
								库存:222
							</text>
						</view>
						<view class="specs">
							<text class="gui-ge">规格:</text>
							<button>0.4</button>
							<button>0.8</button>
						</view>
						<view class="number">
							<text>购买数量:</text>
							<uni-number-box class="number-box"/>
						</view>
						<view class="zong-jia">
							<text>总价:</text>
							<text>￥100元</text>
						</view>
						<view class="add-cart">
							<text>加入购物车</text>
						</view>
					</view>
					
				</view>
			</uni-popup>
		</view>
		
	</view>
</template>

<script>
	import uniLoadMore from "@/components/uni-load-more/uni-load-more.vue"
	import uniCard from "@/components/uni-card/uni-card.vue"
	import uniPopup from "@/components/uni-popup/uni-popup.vue"
	import uniNumberBox from '@/components/uni-number-box/uni-number-box.vue'
	export default {
		components: {
			uniLoadMore,
			uniPopup,
			uniCard,
			uniNumberBox
			},
		data() {
			return {
				loadingType: 'more',
			};
		},
		methods: {
			open:function(){
				this.$refs.popup.open()
				console.log(this.$refs.popup)
						},
			close:function(){
				this.$refs.popup.close()
			},
			change(value) {
				this.numberValue = value
				console.log(value)
			}
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

<style lang="scss">
.mask-screen {
		width: 100%;
		height: 100%;
		position: fixed;
		top: 0;
		left: 0;
		background: #000;
		opacity: 0.5;
		overflow: hidden;
		z-index: 9;
	}

	.region-box {
		width: 100%;
		overflow: hidden;
		position: fixed;
		bottom: 0;
		left: 0;
		z-index: 10;
		background: #fff;
		padding-top: 20upx;
		height: 712upx;
		padding: 40upx 30upx 48upx 30upx;
		box-sizing: border-box;
		display: flex;
		flex-direction: row;
		flex-wrap: wrap;
		align-items: center;
		justify-content: flex-start;
	}
.home-header{
	width: 100%;
	height: 200upx;
	background: #f40;
	display: flex;
	justify-content: space-around;
	align-items: center;
	>.title{
		width: 400upx;
		height: 120upx;
		color: #FFFFFF;
		>.business-firm{
			font-weight: 600;
			font-size: 32upx;
			line-height: 52upx;
		}
		>.address{
			font-size: 24upx;
			line-height: 14upx;
		}
	}
	>image{
		width: 112upx;
		height: 112upx;
	}
}
.banner-part{
	margin: 20upx auto;
	width: 705upx;
	height: 297.5upx;
	image{
		border-radius: 10%;
	}
	>.left-img{
		float: left;
		>image{
			height: 297.5upx;
			width: 345upx;
		}
	}
	>.right-img{
		
		>image{
			padding-left: 15upx;
			height: 145upx;
			width: 345upx;
		}
	}
}
.cargo-part{
	>.goods{
		margin: 0 auto;
		margin-bottom: 80upx;
		width: 700upx;
		height: 260upx;
		.goods-left{
			padding-top: 20upx;
			width: 220upx;
			height: 220upx;
			float: left;
			>image{
				width: 220upx;
				height: 220upx;
			}
		}
		.add{
			float: right;
			margin-top: 200upx;
			>image{
				width: 40upx;
				height: 40upx;
			}
		}
		.goods-right{
			margin-left: 20upx;
			margin-top: 20upx;
			float: right;
			width: 320upx;
			height: 240upx;
			>.goods-name{
				font-size: 32upx;
				width: 100%;
				line-height: 100upx;
			}
			>.aidoudou{
				font-size: 24upx;
				color: #ff6418;
				margin-top: 20upx;
			}
			>.price{
				font-size: 18px;
			}
			>.original-price{
				font-size: 12px;
				color: #878787;
				text-decoration:line-through;
			}
		}
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
