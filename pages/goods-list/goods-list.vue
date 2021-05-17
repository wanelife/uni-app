<template>
	<view class="flex flex-col page-body">
		<view class="">
			<u-search style='margin: 10px;' @search="getGoodslist" @custom="getGoodslist" placeholder="请输入商品名称">
			</u-search>
		</view>
		<view>
			<u-tabs-swiper ref="uTabs" active-color="#c0133c" :list="tabs" :current="current" @change="tabsChange"
				:is-scroll="false" swiperWidth="750"></u-tabs-swiper>
		</view>
		<swiper :current="swiperCurrent" @transition="transition" @animationfinish="animationfinish">
			<swiper-item class="swiper-item" v-for="(item, index) in tabs" :key="index">
				<scroll-view scroll-y style="height: 100%;width: 100%;" @scrolltolower="onreachBottom">
					<navigator url="../goods-detail/goods-detail">
						<view class="goods-item flex " v-for="item in goodsList">
							<image
								src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201509%2F03%2F20150903154259_SJUKi.thumb.700_0.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1622096863&t=7e861223f3e56dfd040c59e4c9cd9429"
								mode=""></image>
							<view class="info flex flex-col j-s">
								<view class="">
									<view class="title bold font16">
										{{item.name}}
									</view>
									<view class="desc c-d">
										销量55 收藏22 人气2356
									</view>
								</view>

								<view class="price bold font16 c-m">
									¥ 678
								</view>
							</view>
						</view>
					</navigator>
				</scroll-view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				cate_id: 0,
				goodsList: [],
				tabs: [{
					name: '人气'
				}, {
					name: '最新'
				}, {
					name: '销量'
				}, {
					name: '价格'
				}],
				// 因为内部的滑动机制限制，请将tabs组件和swiper组件的current用不同变量赋值
				current: 0, // tabs组件的current值，表示当前活动的tab选项
				swiperCurrent: 0, // swiper组件的current值，表示当前那个swiper-item是活动的
			};

		},

		onLoad: function({
			cate_id,
			cate: title
		}) {
			this.cate_id = cate_id
			uni.setNavigationBarTitle({
				title
			});
			this.getGoodslist()
		},
		watch: {
			current() {
				this.getGoodslist()
			}
		},
		methods: {
			getGoodslist() {
				uni.showLoading()
				this.goodsList = []
				setTimeout(() => {
					this.goodsList = Array.from({
							length: 10
						}).map(r => ({
							name: "哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈哈或或或或或或或或或或或或"
						})),
						uni.hideLoading()
				}, 1000)

			},
			tabsChange(index) {
				this.swiperCurrent = index;
			},
			// swiper-item左右移动，通知tabs的滑块跟随移动
			transition(e) {
				let dx = e.detail.dx;
				this.$refs.uTabs.setDx(dx);
			},
			// 由于swiper的内部机制问题，快速切换swiper不会触发dx的连续变化，需要在结束时重置状态
			// swiper滑动结束，分别设置tabs和swiper的状态
			animationfinish(e) {
				let current = e.detail.current;
				this.$refs.uTabs.setFinishCurrent(current);
				this.swiperCurrent = current;
				this.current = current;
			},
			// scroll-view到底部加载更多
			onreachBottom() {

			}
		}

	}
</script>

<style lang="scss">
	swiper {
		flex: 1;
	}

	.goods-item {
		padding: 16rpx;

		image {
			width: 30vw;
			height: 30vw;
			border-radius: 10rpx;
		}

		.info {
			flex: 1;
			padding: 0 16rpx;

			.title {
				line-height: 20px;
				max-height: 40px;
				display: -webkit-box;
				-webkit-box-orient: vertical;
				-webkit-line-clamp: 2;
				overflow: hidden;
				word-break: break-all;
			}

			.desc {
				padding: 10rpx 0;
			}

			.price {
				font-size: 36rpx;
			}
		}
	}
</style>
