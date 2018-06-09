<template>
	<div class="search">
		<input class="search-input" placeholder="输入城市或拼音">
	</div>
</template>

<script>
	export default{
		name:"CitySearch"
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.search
	height: .72rem
	padding: 0 .1rem
	background: $bgColor
	.search-input
		box-sizing:border-box
		// 令border在元素宽度中
		width:100%
		height: .62rem
		padding: 0 .1rem
		line-height: .62rem
		text-align:center
		border-radius: .06rem
		color:#666

</style>

