<template>
	<view class="">
		<view class="search">
			<view class="searchBar">
				<i class="iconfont icon-sousuo"></i>
				<input class="" type="text" />
			</view>
			<view class="searchBtn">搜索</view>
		</view>

		<swiper class="screen-swiper" :class="dotStyle ? 'square-dot' : 'round-dot'" :indicator-dots="true" :circular="true" :autoplay="true" interval="5000" duration="500">
			<swiper-item v-for="(item, index) in swiperList" :key="index">
				<image :src="item.url" mode="aspectFill" v-if="item.type == 'image'"></image>
				<video :src="item.url" autoplay loop muted :show-play-btn="false" :controls="false" objectFit="cover" v-if="item.type == 'video'"></video>
			</swiper-item>
		</swiper>

		<view class="sign"><image src="../../static/shop_banner_boss.gif" mode=""></image></view>

		<view class="icons">
			<view class="icon-item" v-for="(icon, id) in icons" :key="id">
				<view class="icon"><image :src="icon.image" mode=""></image></view>
				<view class="icon-text">{{ icon.text }}</view>
			</view>
			<!-- <view class="icon-item">
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
			</view> -->
		</view>

		<view class="sort">
			<view class="sort-item"><image src="../../static/left.png" mode=""></image></view>
			<view class="sort-item"><image src="../../static/right.png" mode=""></image></view>
		</view>

		<view class="recommend"><image src="../../static/shop_new.jpg" mode=""></image></view>

		<!-- <swiper :interval="3000" :duration="1000"> -->
		<view class="ss">
			<image src="../../static/leftjt.png" mode="" class="jt"></image>
			<image src="../../static/rightjt.png" mode="" class="jt1"></image>
			<view class="s1">
				<view class="swiper-item" v-for="(sp, indexs) in spItem" :key="indexs">
					<image :src="sp.image" mode=""></image>
					<view class="spName">{{ sp.name }}</view>
					<view class="spMoney">{{ sp.money }}</view>
				</view>
			</view>
		</view>
		<!-- </swiper> -->

		<view class="love"><image src="../../static/shop_love.jpg" mode=""></image></view>

		<view class="loveGoods">
			<view class="loveItem">
				<view class="love-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="love-name">商品名字</view>
				<view class="love-price">￥900</view>
			</view>
			<view class="loveItem">
				<view class="love-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="love-name">商品名字</view>
				<view class="love-price">￥900</view>
			</view>
			<view class="loveItem">
				<view class="love-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="love-name">商品名字</view>
				<view class="love-price">￥900</view>
			</view>
		</view>

		<view class="all">
			<image src="../../static/shop_all.jpg" mode=""></image>
			<view class="query-items">
				<view class="query-item">销量</view>
				<view class="query-item">新品</view>
				<view class="query-item">价格</view>
				<view class="query-item">上架时间</view>
				<view class="query-item">筛选</view>
			</view>
		</view>

		<view class="all-items">
			<view class="all-item">
				<view class="all-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="all-name">商品名字</view>
				<view class="all-from">某某旗舰店</view>
				<view class="all-bottom">
					<view class="all-price">￥900</view>
					<view class="all-buy">立刻购买</view>
				</view>
			</view>
			<view class="all-item">
				<view class="all-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="all-name">商品名字</view>
				<view class="all-from">某某旗舰店</view>
				<view class="all-bottom">
					<view class="all-price">￥900</view>
					<view class="all-buy">立刻购买</view>
				</view>
			</view>
			<view class="all-item">
				<view class="all-img"><image src="../../static/sp1.jpg" mode=""></image></view>
				<view class="all-name">商品名字</view>
				<view class="all-from">某某旗舰店</view>
				<view class="all-bottom">
					<view class="all-price">￥900</view>
					<view class="all-buy">立刻购买</view>
				</view>
			</view>
		</view>
		
		<view class="floatRight">
			<view class="me">
				<i class="iconfont icon-wo"></i>
			</view>
			<view class="shopping">
				<i class="iconfont icon-gouwuche"></i>
			</view>
		</view>
	</view>
</template>

<script>
export default {
	data() {
		return {
			swiperList: [
				{
					id: 0,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big84000.jpg'
				},
				{
					id: 1,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big37006.jpg'
				},
				{
					id: 2,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big39000.jpg'
				},
				{
					id: 3,
					type: 'image',
					url: 'https://ossweb-img.qq.com/images/lol/web201310/skin/big10001.jpg'
				}
			],
			dotStyle: true,
			icons: [
				{ image: '../../static/01.gif', text: '冰箱' },
				{ image: '../../static/02.png', text: '冰箱' },
				{ image: '../../static/03.gif', text: '冰箱' },
				{ image: '../../static/04.png', text: '冰箱' },
				{ image: '../../static/05.gif', text: '冰箱' },
				{ image: '../../static/06.png', text: '冰箱' },
				{ image: '../../static/07.png', text: '冰箱' },
				{ image: '../../static/08.png', text: '冰箱' },
				{ image: '../../static/09.gif', text: '冰箱' },
				{ image: '../../static/10.png', text: '冰箱' }
			],
			spItem: [
				{ image: '../../static/sp.jpg', name: '商品名字', money: '￥3000' },
				{ image: '../../static/sp.jpg', name: '商品名字1', money: '￥3000' },
				{ image: '../../static/sp.jpg', name: '商品名字2', money: '￥3300' },
				{ image: '../../static/sp.jpg', name: '商品名字3', money: '￥3200' },
				{ image: '../../static/sp.jpg', name: '商品名字4', money: '￥3100' },
				{ image: '../../static/sp.jpg', name: '商品名字5', money: '￥300' }
			]
		};
	},
	onLoad() {},
	methods: {}
};
</script>

<style>
.search {
	display: flex;
	/* position: fixed;
		top: 50px; */
	width: 100%;
	z-index: 999;
	height: 60upx;
	line-height: 60upx;
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
	background: #fff;
}

.searchBar i {
	font-size: 40upx;
}

.searchBar input {
	padding-left: 2%;
	width: 98%;
	height: 60upx;
	line-height: 60upx;
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
	margin-top: 20upx;
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
	background-color: #ffffff;
}

.icon-item {
	width: 20%;
	margin-top: 30upx;
}

.icon {
	text-align: center;
}

.icon image {
	width: 40px;
	height: 40px;
	border-radius: 100%;
}

.icon-text {
	text-align: center;
}

.sort {
	width: 100%;
	display: flex;
	justify-content: space-between;
	background-color: #ffffff;
}

.sort-item {
	width: 50%;
	padding: 2%;
}

.sort-item image {
	width: 100%;
	/* height: 100%; */
	height: 260upx;
}

.recommend image {
	width: 100%;
	height: 120upx;
}

swiper {
	height: 180px !important;
}

.jt,
.jt1 {
	position: absolute;
	width: 30upx;
	height: 30upx;
	z-index: 999;
	top: 120upx;
}

.jt {
	left: 20upx;
}

.jt1 {
	right: 20upx;
}
.ss {
	position: relative;
}
.s1 {
	display: flex;
	overflow-x: scroll;
}

.swiper-item {
	/* width: 100px !important;
	height: 130px; */
	background-color: #ffffff;
}

.swiper-item image {
	/* width: 100%;
	height: 100%; */
	width: 120px !important;
	height: 130px;
}

.swiper-item .spName {
	text-align: center;
}

.swiper-item .spMoney {
	text-align: center;
	color: red;
}

.love image {
	width: 100%;
	height: 200upx;
}

.loveGoods {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
}

.loveItem {
	/* width:47%; */
	background-color: #ffffff;
	margin: 10upx;
	padding: 10upx;
}

.love-img {
	width: 334upx;
	height: 300upx;
}

.love-img image {
	width: 100%;
	height: 100%;
}

.love-name {
	padding: 10upx;
}

.love-price {
	text-align: center;
	color: red;
}

.all {
	background-color: #ffffff;
}

.all image {
	width: 100%;
	height: 200upx;
}

.query-items {
	display: flex;
	justify-content: space-between;
}

.query-item {
	font-size: 28upx;
	padding: 10upx 30upx;
}

.all-items {
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
}

.all-item {
	background-color: #ffffff;
	margin: 4upx;
	padding: 10upx;
	border-radius: 10px;
}

.all-img {
	width: 346upx;
	height: 300upx;
}

.all-img image {
	width: 100%;
	height: 100%;
}

.all-name {
	/* padding: 10upx; */
}

.all-from {
	color: #666;
	font-size: 24upx;
}

.all-bottom {
	display: flex;
	justify-content: space-between;
}

.all-price {
	text-align: center;
	color: red;
	margin-top: 6upx;
}

.all-buy {
	border: 1px solid red;
	color: red;
	border-radius: 10px;
	padding: 4upx 12upx;
}

.floatRight{
	position: fixed;
	bottom: 120upx;
	right:10upx;
}

.me{
	background-color: #999;
	width:40px;
	height: 40px;
	border-radius: 100%;
	padding-top:10upx;
}

.me i{
	font-size: 60upx;
	color: #FFFFFF;
	padding-left: 10upx;
}

.shopping{
	background-color: #FBBD08;
	width:40px;
	height: 40px;
	border-radius: 100%;
	margin-top:10px;
	padding-top:10upx;
}

.shopping i{
	font-size: 60upx;
	color: #FFFFFF;
	padding-left: 10upx;
	
}
</style>
