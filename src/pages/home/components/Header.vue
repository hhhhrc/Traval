<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
	<router-link to='/city'>
		<div class="header-input">
		<span class="iconfont">&#xe632;</span>
		输入城市/景点/游玩主题
		</div>
	</router-link>
		<router-link to='/city'>
			<div class="header-right">
				<!-- {{this.$store.state.city}} -->
				{{this.city}}
				<span class="iconfont arrow-icon">&#xe64a;</span>
			</div>
		</router-link>
	</div>
</template>

<script>
	import {mapState} from 'vuex'
	export default{
		name:'HomeHeader',
		computed:{
			...mapState(['city'])
		},		
// 把city这个公用数据映射到名为city的计算属性中
	}
</script>

<style lang="stylus" scoped>
// @import '../../../assets/styles/varibles.styl'
// @import '~@/assets/styles/varibles.styl'
// @指向src目录,样式里引入样式前面加~,import前面加@
@import '~styles/varibles.styl'
.header
	line-height: $headerHeight
	background:$bgColor
	color:#fff
	.header-left
		display inline-block
		width: 10%

		.back-icon
			text-align:center
			font-size: .4rem
	.header-input
		display:inline-block
		width:66%
		height: .64rem
		line-height: .64rem
		margin-top: .12rem
		margin-left: .2rem
		padding-left: .2rem
		background: #fff
		border-radius: .1rem
		color: #ccc
	.header-right
		float right
		display:inline-block
		min-width: 1.04rem
		padding: 0 .1rem
		text-align:center
		color:#fff
		.arrow-icon
			margin-left:-.04rem
			font-size: .24rem
</style>

<!-- 1rem 50px -->
<!-- 1px 0.02rem -->
