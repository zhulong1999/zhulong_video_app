<template>
	<view id="page">
		<view class="nav">
			<uni-nav-bar :fixed="false" color="#FF6B69" background-color="#FFFFFF" right-icon="scan" @clickLeft="showCity" @clickRight="scan" status-bar="true">
				<block slot="left">
					<view class="city">
						<view><text class="uni-nav-bar-text">烛龙影视</text></view>
					</view>
				</block>
				<view class="input-view">
					<uni-icons class="input-uni-icon" type="search" size="22" color="#666666" />
					<input confirm-type="search" class="nav-bar-input" type="text" placeholder="输入搜索关键词" @confirm="confirm" />
				</view>
			</uni-nav-bar>
		</view>
		<scroll-view scroll-y="true" refresher-enabled="true" refresher-default-style='white'>
			<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000">
				<swiper-item v-for="item in banner">
					<view class="swiper-item"><image :src="item.image" mode="" style="width: 100%;"></image></view>
				</swiper-item>
			</swiper>
		</scroll-view>
	</view>
</template>

<script>
// console.log(uni.getSystemInfoSync());
import uniIcons from '@/components/uni-icons/uni-icons.vue';
import uniNavBar from '@/components/uni-nav-bar/uni-nav-bar.vue';
export default {
	components: {
		uniIcons,
		uniNavBar
	},
	data() {
		return {
			banner: [
				{
					image: 'https://dss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=2738217414,2499894487&fm=179&app=42&f=JPEG?w=121&h=140&s=9CE1E904CD52BEDC6A6CF8820100E093'
				}
			]
		};
	}
};
</script>

<style>
/* 头条小程序组件内不能引入字体 */
/* #ifdef MP-TOUTIAO */
@font-face {
	font-family: uniicons;
	font-weight: normal;
	font-style: normal;
	src: url('~@/static/uni.ttf') format('truetype');
}

/* #endif */

/* #ifndef APP-NVUE */

view {
	font-size: 14px;
	line-height: inherit;
}

/* #endif */

.word-btn-white {
	font-size: 18px;
	color: #ffffff;
}

.uni-nav-bar-text {
	font-size: 28rpx;
}

.city {
	/* #ifndef APP-PLUS-NVUE */
	display: flex;
	/* #endif */
	flex-direction: row;
	align-items: center;
	justify-content: flex-start;
	/* width: 160rpx;
 */
	margin-left: 4px;
}

.input-view {
	/* #ifndef APP-PLUS-NVUE */
	display: flex;
	/* #endif */
	flex-direction: row;
	/* width: 500rpx;
 */
	flex: 1;
	background-color: #f8f8f8;
	height: 30px;
	border-radius: 15px;
	padding: 0 15px;
	flex-wrap: nowrap;
	margin: 7px 0;
	line-height: 30px;
}

.input-uni-icon {
	line-height: 30px;
}

.nav-bar-input {
	height: 30px;
	line-height: 30px;
	/* #ifdef APP-PLUS-NVUE */
	width: 370rpx;
	/* #endif */
	padding: 0 5px;
	font-size: 28rpx;
	background-color: #f8f8f8;
}
</style>
