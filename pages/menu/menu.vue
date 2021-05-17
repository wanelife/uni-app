<template>
	<view class="flex flex-col page-body-tab">
		

		<view class="container flex">
			<view class="menu">
				<view class="item" @click="active=i" :class='{active:i===active}' v-for="(item,i) in menus">
					{{item}}
				</view>
			</view>
			<view class="sub-menu ">
				<u-grid :col="3" :border="false">
					<u-grid-item v-for="item in sub_menu">
						<navigator :url='`../goods-list/goods-list?cate_id=${item.id}&cate=${item.name}`'>
							<image
								src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fwww.17qq.com%2Fimg_qqtouxiang%2F89268307.jpeg&refer=http%3A%2F%2Fwww.17qq.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1621925874&t=5e65f235b7a78c96b9cf958a11c582d2"
								mode=""></image>
							<view class="grid-text">{{item.name}}</view>
						</navigator>	
					</u-grid-item>
				</u-grid>


			</view>
		</view>

	</view>
</template>

<script>
	export default {
		data() {
			return {
				active: 3,
				menus: [
					"服装",
					"食品",
					"饰品",
					"家具"
				],
				sub_menu:[
					{
						id:1,
						name:"休闲零食"
					},
					{
						id:2,
						name:"坚果系列"
					},
					{
						id:3,
						name:"米面主食"
					},
				]

			}
		},
		methods: {

		}
	}
</script>

<style lang="scss">
	.container {
		flex: 1;

		.menu {
			width: 200rpx;
			background: #eee;
			text-align: center;

			.item {
				padding: 10rpx;
				letter-spacing: 2rpx;
				border-left: 6rpx solid transparent;

				&.active {
					background: #fff;
					border-left: 6rpx solid $main-color;
					font-weight: bold;
					color: $main-color;
				}
			}

		}

		.sub-menu {
			flex: 1;
			align-content: flex-start;

			padding: 10rpx 0rpx;

			image {
				width: 18vw;
				border: 1rpx solid #2B85E4;
				border-radius: 50%;
				height: 18vw;
			}
		}

	}
</style>
