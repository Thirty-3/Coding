<template>
	<view>
	<view class="waterfall" :style='{paddingRight: space + "px"}'>
		<view class="ul" v-for="(list, idx) in dataList" :key='idx'>
      <view class="item" v-for="(item, index) in list" :key='index' :style='{marginLeft: space + "px", marginTop: space + "px", width: itemWidth + "px"}'>
        <image class="cover" mode='widthFix' :src="item.url"  @tap="$Router.push({name:'details'})"></image>
		<text class="goods-name">测试商品</text>
		<br />
		<text class="aidoudou">爱豆豆:0个</text>
		<br />
		<text class="price">￥2000</text>
		<text class="original-price">￥3000</text>
		<view  @click="open" class="add">
			<image src="../../static/img/home/add.png" mode=""></image>
		</view>
      </view>
    </view>
	</view>
	
	
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
	import uniPopup from "@/components/uni-popup/uni-popup.vue"
	import uniNumberBox from '@/components/uni-number-box/uni-number-box.vue'
	export default {
components: {
			uniNumberBox,
			uniPopup
			},
    props: {
      list: {  // 页面列表数据
        type: Array,
        default: []
      },
      column: {
        type: Number
      }, // 显示列数
      space: {
        type: Number
      }, // 图片间间隔
    },
		data() {
			return {
				dataList: [],
        totalHeight: [],
        itemWidth: 0
			};
		},
    watch: {
      list: {
        deep: true,
        handler (newList, oldList) {
          // if (newList.length === 0) {
          //   this.dataList = []
          //   this.totalHeight = []
          //   return
          // }
          let dataList = []
          let totalHeight = []
          this.column = this.column < 2 ? 2 : this.column
          let itemWidth = parseInt((uni.getSystemInfoSync().windowWidth - (this.column + 1) * this.space) / this.column)
          if (this.dataList.length === 0) {
            for (let i = 0; i < this.column; i++) {
              dataList.push([])
            }
            totalHeight = new Array(this.column).fill(0)
          } else {
            dataList = JSON.parse(JSON.stringify(this.dataList))
            totalHeight = JSON.parse(JSON.stringify(this.totalHeight))
          }
          let nList = newList.filter(newItem => {
            let b = true
            oldList.forEach(oldItem => {
              if (newItem.url === oldItem) {
                b = false
              }
            })
            return b
          })
          nList.forEach(item => {
            let minIndex = this.getMinIndex(totalHeight)
            totalHeight[minIndex] += parseInt(item.height * (itemWidth / item.width))
            dataList[minIndex].push(item)
          })
          this.dataList = dataList
          this.totalHeight = totalHeight
          this.itemWidth = itemWidth
        }
      }
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
		},
      getMinIndex (totalHeight) {
        let minIndex = 0
        let minValue = totalHeight[0]
        for (let i = 0; i < totalHeight.length; i++) {
          if (totalHeight[i] < minValue) {
            minIndex = i
          }
        }
        return minIndex
      }
    }
	}
</script>

<style lang="scss">
  .waterfall {
    background: #f8f8f8;
    .ul {
      display: inline-block;
      vertical-align: top;
      .item {
		  text-align: left;
		  .goods-name{
			  font-size: 26upx;
		  }
		  .aidoudou{
			font-size: 24upx;
			color: #ff6818;
			line-height: 60upx;  
		  }
		  .price{
			  font-size: 30upx;
		  }
		  .original-price{
			font-size: 24upx;
			color: #d1d0d0;
			margin-left: 6upx;
		  }
		 .add{
		 	float: right;
		 	margin-top: 10upx;
		 	>image{
		 		width: 40upx;
		 		height: 40upx;
		 	}
		 }
        .cover {
          width: 100%;
          vertical-align: top;
          border-radius: 8upx;
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
