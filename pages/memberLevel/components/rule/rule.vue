<template>
	<view class="rule">
		<view class="rule-top">
			<image class="rule-top-image" src="../../../../static/image/memberLevel/rule.png" mode="widthFix"></image>
			<view class="rule-top-text">
				<view class="rule-top-text-dengji">
					当前等级
				</view>
				<view class="rule-top-text-duanwei">
					青铜
				</view>
				<view class="rule-top-text-quanyi">
					尊享3大权益
				</view>
				<view class="rule-top-text-guize">
					等级规则
					<view class="rule-top-text-guize-wenhao"></view>
				</view>
			</view>
		</view>
		<view class="rule-bottom">
			<view 
			v-for="(item,index) in list" 
			:key='index' 
			@click="activShow(index)"
			:class="{'rule-bottom-activ':currentLevel>index||currentClick>currentLevel&&currentLevel==index,'rule-bottom-activ-border':currentLevel>index}"
			>
				<icon 
				v-if="(currentLevel==index && currentClick <= currentLevel)||(currentClick==index&&currentClick>currentLevel)"
				class="rule-bottom-icon" 
				:class="{'rule-bottom-icon-activ':currentClick == index&&index > currentLevel}"
				type="success_no_circle" 
				size="14"
				color='#ffffff'
				></icon>
				<view>
					{{item}}
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name:'rule',
		data(){
			return {
				list:['青铜','白银','黄金','铂金','砖石'],
				currentLevel:2,
				currentClick:0
			}
		},
		methods:{
			activShow(index){
				this.currentClick = index
			}
		}
	}
</script>
<style lang="scss">
	.rule{
		.rule-top{
			width: 100%;
			position: relative;
			box-shadow: 0rpx 6rpx 10rpx rgba(221,221,221,1);
			border-radius: 20rpx;
			.rule-top-image{
				width: 100%;
				display: block;
			}
			.rule-top-text{
				position: absolute;
				top: 0;
				left: 0;
				bottom: 0;
				right: 0;
				.rule-top-text-dengji{
					width: 120rpx;
					height: 44rpx;
					background-color: #F2C7A9;
					font-size: 24rpx;
					color: #FFFFFF;
					line-height: 44rpx;
					text-align: center;
					letter-spacing: 2rpx;
					border-top-left-radius: 20rpx;
					border-bottom-right-radius: 25rpx;
				}
				.rule-top-text-duanwei{
					font-size: 40rpx;
					color: #73553D;
					margin-top: 12rpx;
					margin-left: 44rpx;
					font-weight: 700;
					letter-spacing: 2rpx;
				}
				.rule-top-text-quanyi{
					font-size: 26rpx;
					color: #73553D;
					margin-top: 12rpx;
					margin-left: 44rpx;
					letter-spacing: 1rpx;
				}
				.rule-top-text-guize{
					font-size: 24rpx;
					color: #666666;
					position: absolute;
					top: 60rpx;
					right: 86rpx;
					.rule-top-text-guize-wenhao{
						width: 26rpx;
						height: 26rpx;
						position: absolute;
						top: 0;
						bottom: 0;
						right: -8rpx;
						margin: auto 0;
						border: 1px solid #8A8A8A;
						border-radius: 50%;
						transform: translateX(100%);
						box-sizing: border-box;
						&::before{
							content: "?";
							line-height: 1;
							position: absolute;
							bottom: 50%;
							right: 50%;
							font-size: 22rpx;
							color: #8A8A8A;
							transform: translateX(50%) translateY(50%);
						}
					}
				}
			}
		}
		.rule-bottom{
			padding: 50rpx 70rpx 72rpx 70rpx;
			box-sizing: border-box;
			display: flex;
			justify-content: space-between;
			position: relative;
			.rule-bottom-icon{
				position: absolute;
				top: 50%;
				left: 50%;
				transform: translateX(-50%) translateY(-50%);
				border-radius: 50%;
				background-color: #F9446D;
				padding: 6rpx;
				&.rule-bottom-icon-activ{
					background-color: #999999;
				}
			}
			&::before{
				content: '';
				height: 4rpx;
				background-color: #EBEBEB;
				position: absolute;
				top: 50rpx;
				left: 70rpx;
				right: 70rpx;
				bottom: 72rpx;
				margin: auto 0;
				z-index: 10;
			}
			&>view{
				width: 28rpx;
				height: 28rpx;
				border-radius: 50%;
				border: 2rpx solid #999999;
				box-sizing: border-box;
				background-color: #F7F7F7;
				z-index: 20;
				position: relative;
				&.rule-bottom-activ-border{
					border-color: transparent;
				}
				&.rule-bottom-activ::before{
					content: '';
					width: 40rpx;
					height: 40rpx;
					border-radius: 50%;
					box-sizing: border-box;
					border: 6rpx solid rgba(249,68,109,0.3);
					background-color: #F9446D;
					background-clip: content-box;
					box-sizing: border-box;
					position: absolute;
					top: 50%;
					left: 50%;
					transform: translateX(-50%) translateY(-50%);
				}
				&>view{
					font-size: 24rpx;
					color: #999999;
					position: absolute;
					left: 50%;
					bottom: -10rpx;
					white-space: nowrap;
					letter-spacing: 2rpx;
					transform: translateX(-50%) translateY(100%);
				}
			}
		}
	}
</style>
