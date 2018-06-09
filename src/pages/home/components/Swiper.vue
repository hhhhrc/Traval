<template>
	<div class="wrapper">
	<swiper :options="swiperOption" v-if="showSwiper">
		<!-- 由于下面一开始是以空数组创建,会从最后一张图开始显示,上面设置了不是空数组才创建 -->
		<!-- slides -->
		<swiper-slide v-for="item of list" :key="item.id">
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
		props:{
			list:Array
		},
		data () {
			return{
				swiperOption:{
					pagination:'.swiper-pagination',
					loop:true
				}
			}
		},
		computed:{
			showSwiper(){
				return this.list.length
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
	padding-bottom:26.5%
	backgroundcolor:#eee
	.swiper-img
		width:100%
</style>
