<template>
	<div class="icons">
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
		<div class="icon">
			<div class="icon-img">
				<img class="icon-img-content" src="http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png">
			</div>
			<p class="icon-desc">景点门票</p>
		</div>
	</div>
</template>

<script>
	export default{
		name:'HomeIcons'
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
	.icons
		overflow:hidden
		width:100%
		height:0
		padding-bottom:50%
		.icon
			position:relative
			overflow:hidden
			float:left
			height:0
			width:25%
			padding-bottom:25%
			.icon-img
				position:absolute
				top:0
				left:0
				right:0
				box-sizing:border-box
				padding: .1rem
				bottom: .44rem
				.icon-img-content
					display:block
					margin:0 auto
					height:100%
			.icon-desc
				position:absolute
				left:0
				right:0
				bottom:0
				height: .44rem
				line-height: .44rem
				text-align:center
				color:$darkTextColor
</style>