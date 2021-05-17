<template>
	<view>
		<swiper class = "swiper" autoplay circular indicator-dots indicator-color="#fff" indicator-active-color="green">
			<swiper-item>
				<image  src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fpic1.win4000.com%2Fwallpaper%2F2018-06-07%2F5b18d6f827ad2.jpg&refer=http%3A%2F%2Fpic1.win4000.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619618027&t=de411ccfccf8d316311757fbfc3b89be" ></image>
			</swiper-item>
			<swiper-item>
				<image  src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fb-ssl.duitang.com%2Fuploads%2Fitem%2F201701%2F12%2F20170112153336_4iVjf.jpeg&refer=http%3A%2F%2Fb-ssl.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619618144&t=233dee9285dd66935ceca3bb62066758" ></image>
			</swiper-item>
			<swiper-item>
				<image  src="https://gimg2.baidu.com/image_search/src=http%3A%2F%2Fcdn.duitang.com%2Fuploads%2Fitem%2F201209%2F06%2F20120906144844_tfCRK.jpeg&refer=http%3A%2F%2Fcdn.duitang.com&app=2002&size=f9999,10000&q=a80&n=0&g=0n&fmt=jpeg?sec=1619618210&t=d7787eb797a56caccd76f8f8e35b6a1e" ></image>
			</swiper-item>
		</swiper>
		
	</view>
</template>

<script>
	export default {
		name:"Banner",
		data() {
			return {
				
			};
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

</style>
