<template>
	<div>
		<div class="title">热销推荐</div>
		<ul>
			<li class="item border-bottom" 
			v-for="item of recommendList"
			:key='item.id'>
				<img class="item-img" :src=item.imgUrl />
				<div class="item-info">
					<p class="item-title">{{item.title}}</p>
					<p class="item-desc">{{item.desc}}</p>
					<button class="item-button">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default{
		name:'HomeRecommend',
		data(){
			return{
				recommendList:[{
					id:'0001',
					imgUrl:'http://img1.qunarzz.com/sight/p0/1504/47/4730a0c01664b63d.water.jpg_200x200_d7f52253.jpg',
					title:'武汉海昌极地海洋世界',
					desc:'武汉第一站,浪漫的海洋主题乐园'
				},{
					id:'0002',
					imgUrl:'http://img1.qunarzz.com/sight/p0/1705/99/99cad7081abb9771a3.img.jpg_200x200_d86753f0.jpg',
					title:'知音号游船',
					desc:'登上大型轮船，观看触及心灵的武汉故事'
				},{
					id:'0003',
					imgUrl:'http://img1.qunarzz.com/sight/p0/1505/bb/bb978d0b35e4965c.water.jpg_200x200_d705f205.jpg',
					title:'汉秀剧场',
					desc:'🔥好评如潮，小伙伴热推景点~'
				}]
				}
		}
	}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
	.title
		margin-top: .2rem
		line-height: .8rem
		background: #eee
		text-indent: .2rem
	.item
		overflow:hidden
		display:flex
		height:1.9rem
		.item-img
			width: 1.7rem
			height: 1.7rem
			padding: .1rem
		.item-info
			flex:1
			padding: .1rem
			min-width: 0
			.item-title
				line-height: .54rem
				font-size: .32rem
			.item-desc
				line-height: .4rem
				color: #ccc
				ellipsis()
			.item-button
				line-height: .44rem
				margin-top: .16rem
				background: #ff9300
				padding: 0 .2rem
				border-radius: .06rem
				color: #fff
</style>