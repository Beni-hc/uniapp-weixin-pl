<template>
	<view class="member-level">
		<view class="member-level-rule">
			<rule></rule>
		</view>
		<view class="member-level-quanyi">
			<view class="member-level-quanyi-title">
				<view>
					<text>
						等级权益
					</text>
				</view>
			</view>
			<view class="member-level-quanyi-content">
				<view v-for="(item,index) in 6" :key='index' class="member-level-quanyi-content-item">
					<image src="../../static/image/test/4@2x.png" mode="aspectFill"></image>
					<view>
						拼团成功返3人总额的50%代金券
					</view>
				</view>
			</view>
			<view class="member-level-quanyi-footer">
				推广会员
			</view>
		</view>
		<view v-if="isShow" class="member-level-pingji">
			<view class="member-level-pingji-title">
				<view>
					<text>
						会员评级进度
					</text>
				</view>
			</view>
			<view class="member-level-pingji-content">
				<view class="member-level-pingji-content-title">
					当前有效活跃值
				</view>
				<view class="member-level-pingji-content-bfb">
					<progress 
					percent="50"
					border-radius='8rpx' 
					activeColor='#F9446D'
					backgroundColor='#F7F7F7'
					stroke-width='8px'
					/>
					<text>0/1000</text>
				</view>
				<view class="member-level-pingji-content-text">
					每日数据次日6:00更新，每月数据1-3号更新
				</view>
				<view class="member-level-pingji-content-item">
					<view>
						<view>
							本月有效拉新0人
						</view>
						<view>
							+0积分>
						</view>
					</view>
					<view>
						<view>
							本月有效订单0元
						</view>
						<view>
							+0积分>
						</view>
					</view>
				</view>
			</view>
		</view>
		<view v-if="!isShow" class="member-level-huiyuan">
			<view class="member-level-huiyuan-title">
				<view>
					<text>
						解锁钻石会员
					</text>
				</view>
			</view>
			<view class="member-level-huiyuan-text">
				购买以下商品消费5000元即可解锁
			</view>
			<view class="member-level-huiyuan-list">
				aaaa
			</view>
		</view>
	</view>
</template>

<script>
	import rule from './components/rule/rule.vue'
	export default {
		data() {
			return {
				isShow:false
			}
		},
		methods: {
			
		},
		components:{
			rule
		}
	}
</script>

<style lang="scss">
	.member-level{
		background-color: #F7F7F7;
		padding-top: 2rpx;
		.member-level-rule{
			padding: 40rpx 24rpx 0rpx 24rpx;
			box-sizing: border-box;
			background-color: #FFFFFF;
			margin-bottom: 20rpx;
		}
		.member-level-quanyi{
			background-color: #FFFFFF;
			padding: 26rpx 24rpx 22rpx;
			margin-bottom: 20rpx;
			box-sizing: border-box;
			.member-level-quanyi-title{
				display: flex;
				margin-bottom: 20rpx;
				&>view{
					position: relative;
					&>text{
						font-size: 32rpx;
						color: #333333;
						letter-spacing: 2rpx;
						position: relative;
						z-index: 20;
					}
					&::before{
						content: '';
						height: 16rpx;
						position: absolute;
						left: 0;
						right: 0;
						bottom: -6rpx;
						background-color: #FFE1E7;
						z-index: 10;
					}
				}
			}
			.member-level-quanyi-content{
				padding-top: 28rpx;
				box-sizing: border-box;
				display: flex;
				flex-flow: wrap;
				justify-content: space-between;
				.member-level-quanyi-content-item{
					display: flex;
					flex-flow: column;
					align-items: center;
					margin-bottom: 28rpx;
					margin-right: 80rpx;
					&:nth-child(3n){
						margin-right:0
					}
					&>image{
						width: 60rpx;
						height: 60rpx;
						display: block;
						margin-bottom: 20rpx;
					}
					&>view{
						width: 170rpx;
						height: 118rpx;
						font-size: 24rpx;
						color: #666666;
						letter-spacing: 1rpx;
						text-align: center;
						line-height: 1.5;
					}
				}
			}
			.member-level-quanyi-footer{
				width: 480rpx;
				height: 80rpx;
				background-color: #F9446D;
				font-size: 34rpx;
				color: #FFFFFF;
				line-height: 80rpx;
				text-align: center;
				border-radius: 40rpx;
				margin: 0 auto 8rpx;
				box-shadow: 0rpx 6rpx 12rpx rgba(249, 68, 109, 0.4);
			}
		}
		.member-level-pingji{
			background-color: #FFFFFF;
			padding: 26rpx 24rpx 22rpx;
			box-sizing: border-box;
			.member-level-pingji-title{
				display: flex;
				margin-bottom: 32rpx;
				&>view{
					position: relative;
					&>text{
						font-size: 32rpx;
						color: #333333;
						letter-spacing: 2rpx;
						position: relative;
						z-index: 20;
					}
					&::before{
						content: '';
						height: 16rpx;
						position: absolute;
						left: 0;
						right: 0;
						bottom: -2rpx;
						background-color: #FFE1E7;
						z-index: 10;
					}
				}
			}
			.member-level-pingji-content{
				.member-level-pingji-content-title{
					font-size: 28rpx;
					color: #666666;
					letter-spacing: 1rpx;
				}
				.member-level-pingji-content-bfb{
					margin: 16rpx 0;
					position: relative;
					&>progress{
						width: 480rpx;
						height: 8px;
					}
					&>text{
						position: absolute;
						right: 0;
						top: 50%;
						transform: translateY(-50%);
						font-size: 32rpx;
						color: #333333;
						line-height: 1;
					}
				}
				.member-level-pingji-content-text{
					font-size: 24rpx;
					color: #999999;
				}
				.member-level-pingji-content-item{
					border-radius: 10rpx;
					position: relative;
					overflow: hidden;
					margin: 26rpx 0 22rpx 0;
					&>view{
						height: 100rpx;
						padding: 0 30rpx 0 26rpx;
						display: flex;
						justify-content: space-between;
						align-items: center;
						box-sizing: border-box;
						background-color: #FFF3F6;
						&>view{
							&:first-child{
								font-size: 28rpx;
								color: #666666;
								letter-spacing: 1rpx;
							}
							&:last-child{
								font-size: 24rpx;
								color: #999999;
								letter-spacing: 1rpx;
							}
						}
					}
					&::before{
						content: '';
						height: 1rpx;
						background-color: #F0F0F0;
						position: absolute;
						top: 0;
						left: 30rpx;
						bottom: 0;
						right: 30rpx;
						margin: auto 0;
						z-index: 50;
					}
				}
			}
		}
		.member-level-huiyuan{
			background-color: #FFFFFF;
			padding: 26rpx 24rpx 22rpx;
			box-sizing: border-box;
			.member-level-huiyuan-title{
				display: flex;
				margin-bottom: 16rpx;
				&>view{
					position: relative;
					&>text{
						font-size: 32rpx;
						color: #333333;
						letter-spacing: 2rpx;
						position: relative;
						z-index: 20;
					}
					&::before{
						content: '';
						height: 16rpx;
						position: absolute;
						left: 0;
						right: 0;
						bottom: -2rpx;
						background-color: #FFE1E7;
						z-index: 10;
					}
				}
			}
			.member-level-huiyuan-text{
				font-size: 24rpx;
				color: #999999;
				line-height: 1;
				letter-spacing: 1rpx;
			}
			.member-level-huiyuan-list{
				padding-top: 28rpx;
				display: flex;
				flex-flow: wrap;
				justify-content: space-between;
			}
		}
		
	}
</style>
