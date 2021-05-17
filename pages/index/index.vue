<template>
	<view class="content">
		<u-search style='margin: 10px;' placeholder="日照香炉生紫烟" ></u-search>
		<Banner/>
		<u-notice-bar mode="horizontal" :list="list"></u-notice-bar>
		<view class="rec-goods-list flex">
			<view class="item flex flex-col a-c" v-for="item in 10">
				<image src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Finews.gtimg.com%2Fnewsapp_match%2F0%2F10775327393%2F0.jpg&refer=http%3A%2F%2Finews.gtimg.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1621601605&t=aaec143412eca31cabcfb054333267ab" mode=""></image>
				<view class="goods-name">
					美美美
				</view>
				<view class="goods-price">
					￥2555
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list:['大家好，本网站将于2月18日期间放价。'
				]
			}
		},
		onLoad() {
			

		},
		methods: {
			

		}
	}
</script>

<style lang="scss" scoped>
	.swiper {
		width: 100%;
		height: 350rpx;
		image{
			height: 100%;
			width: 100%;
		}
		
	}
	.rec-goods-list{
		
		.item{
			&:active{
				box-shadow: 0 0 4rpx #ccc;
			}
			box-shadow: 0 0 2rpx #ccc;
			width: 50%;
			padding: 20rpx;
			image{
				width: 90%;
				height: 360rpx;
			}
			
			.goods-name{
				font-weight: bold;
			}
			.goods-price{
				color: $uni-color-error;
				font-weight: bold;
			}
		}
	}
	
</style>
