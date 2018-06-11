<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" src="http://img1.qunarzz.com/sight/p0/1507/92/878bc1fd0e41d1eb1dd011b8cbdf60b7.water.jpg_r_800x800_d9c8595b.jpg"/>
			<div class="banner-info">
				<div class="banner-title">
					北京野生动物园(AAAA景区)
				</div>
				<div class="banner-number">
					<span class="iconfont bannner-icon">&#xe692;</span> 2
				</div>
			</div>
		</div>
		<common-gallary 
		:imgs="imgs" 
		v-show="showGallary"
		@close="handleGallaryClose"
		></common-gallary>
	</div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
export default{
	name:"DetailBanner",
	data(){
		return{
			showGallary: false,
			imgs:["http://img1.qunarzz.com/sight/p0/1507/92/878bc1fd0e41d1eb1dd011b8cbdf60b7.water.jpg_r_800x800_d9c8595b.jpg","http://img1.qunarzz.com/sight/p0/1508/40/cba8d15891dc025cc7e629a0678fa811.water.jpg_r_800x800_708e16ca.jpg"]
		}
	},
	methods:{
		handleBannerClick(){
			this.showGallary=true
		},
		handleGallaryClose(){
			this.showGallary=false

		}
	},
	components:{
		CommonGallary
		}
	}
</script>

<style lang="stylus" scoped>
	.banner
		position:relative
		overflow: hidden
		height:0
		padding-bottom: 55%
		.banner-img
			width:100%
		.banner-info
			display:flex
			position: absolute
			left:0
			right:0
			bottom:0
			line-height: .6rem
			color:#fff
			background-image:linear-gradient(top,rgba(0,0,0,0,),rgba(0,0,0,0.8))
			.banner-title
				flex:1
				font-size: .32rem
				padding:0 .2rem
			.banner-number
				height: .32rem
				line-height: .32rem
				margin-top: .14rem
				padding:0 .4rem
				border-radius: .2rem
				background:rgba(0,0,0, .8)
				font-size: .24rem
				.bannner-icon
					font-size: .24rem
				


</style>
