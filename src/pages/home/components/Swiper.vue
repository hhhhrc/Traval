<template>
	<div class="wrapper">
	<swiper :options="swiperOption">
		<!-- slides -->
		<swiper-slide v-for="item of swiperlist" :key="item.id">
			<img class="swiper-img" :src="item.imgUrl">
		</swiper-slide>
		<!-- Optional controls -->
		<div class="swiper-pagination"  slot="pagination"></div>
	</swiper>
		</div>
</template>

<script>
	export default{
		name:'HomeSwiper',
		data () {
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				},
				swiperlist:[{
					id:'0001',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1805/66/f87b0d1f49ab4c02.jpg_750x200_dfab2c85.jpg'
				},{
					id:'0002',
					imgUrl:'http://img1.qunarzz.com/piao/fusion/1804/b5/8bd6da9d794e1902.jpg_750x200_b1a28179.jpg'
				}]
			}
		}
	}
</script>

<style lang="stylus" scoped>
.wrapper >>>.swiper-pagination-bullet-active
	background: #fff
// 防止抖动,高度设为0 ,使其自动撑开
.wrapper
	overflow: hidden
	width:100%
	height:0
	padding-bottom:31.25%
	backgroundcolor:#eee
	.swiper-img
		width:100%
</style>
