<template>
	<view class="">
		<view class="search">
			<view class="searchBar">
				<i class="iconfont icon-sousuo"></i><input class="" type="text">
			</view>
			<view class="searchBtn">
				搜索
			</view>
		</view>

		<swiper class="screen-swiper" :class="dotStyle?'square-dot':'round-dot'" :indicator-dots="true" :circular="true"
		 :autoplay="true" interval="5000" duration="500">
			<swiper-item v-for="(item,index) in swiperList" :key="index">
				<image :src="item.url" mode="aspectFill" v-if="item.type=='image'"></image>
				<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type=='video'"></video>
			</swiper-item>
		</swiper>

		<view class="sign">
			<image src="../../static/2.jpg" mode=""></image>
		</view>

		<view class="icons">
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
			<view class="icon-item">
				<view class="icon">
					<image src="../../static/3.jpg" mode=""></image>
				</view>
				<view class="icon-text">
					冰箱
				</view>
			</view>
		</view>
		
		<view class="sort">
			<view class="sort-item">
				<image src="../../static/logo.png" mode=""></image>
			</view>
			<view class="sort-item">
				<image src="../../static/logo.png" mode=""></image>
			</view>
		</view>
		
		<view class="recommend">
			<image src="../../static/5.jpg" mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swiperList: [{
					id: 0,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
				}, {
					id: 1,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg',
				}, {
					id: 2,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
				}, {
					id: 3,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg'
				}],
				dotStyle: true

			}
		},
		onLoad() {
			this.TowerSwiper('swiperList');
		},
		methods: {

		}
	}
</script>

<style>
	.search {
		display: flex;
		/* position: fixed;
		top: 50px; */
		width: 100%;
		z-index: 999;
		height: 80upx;
		line-height: 80upx;
		margin-top: 10px;
		/* background-color: #ddd; */
	}

	.searchBar {
		width: 70%;
		display: flex;
		padding: 0upx 2%;
		margin: 0upx auto;
		border: 1px solid #ccc;
		border-radius: 20px;
		background:#fff;
	}

	.searchBar i {
		font-size: 40upx;
	}

	.searchBar input {
		padding-left: 2%;
		width: 98%;
		height: 80upx;
		line-height: 80upx;
	}

	.searchBtn {
		background-color: red;
		border-radius: 20upx;
		width: 15%;
		color: #fff;
		padding: 4upx 2%;
		margin-right: 5%;
		font-size: 32upx;
		text-align: center;
	}

	/* 轮播图 */
	.screen-swiper {
		margin-top: 20px;
	}

	.sign image {
		width: 100%;
		height: 150px;
	}

	.icons {
		width: 100%;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-between;
	}

	.icon-item {
		width: 20%;
		margin-top:30upx;
	}
	
	.icon{
		text-align: center;
	}

	.icon image {
		width: 40px;
		height: 40px;
		border-radius: 100%;
		
	}
	
	.icon-text{
		text-align: center;
	}
	
	.sort{
		width:100%;
		display: flex;
		justify-content: space-between;
	}
	
	.sort-item{
		width:50%;
		padding:2%;
		
	}
	
	.sort-item image{
		width: 100%;
		height: 200upx;
	}
	
	.recommend image{
		width:100%;
		height: 160upx;
	}
</style>
