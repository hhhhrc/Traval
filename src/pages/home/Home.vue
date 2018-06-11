<template>
	<div>
		<home-header></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>
	</div>
</template>

<script>
	import axios from 'axios'
	import HomeHeader from './components/Header'
	import HomeSwiper from './components/Swiper'
	import HomeIcons from './components/Icons'
	import HomeRecommend from './components/Recommend'
	import HomeWeekend from './components/Weekend'
	export default{
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend,
			HomeWeekend
		},
		data () {
				return {
					swiperList: [],
					iconList:[],
					recommendList:[],
					weekendList:[]
				}
		},
		methods:{
			getHomeInfo () {
				axios.get('/api/index.json')
					.then(this.getHomeInfoSucc)
			},
			getHomeInfoSucc(res){
				res=res.data
				if(res.ret&&res.data){
					const data=res.data
					this.swiperList=data.swiperList
					this.iconList=data.iconList
					this.recommendList=data.recommendList
					this.weekendList=data.weekendList
				}
			}
		},
		mounted ( ) {
			this.getHomeInfo( )
		}
	}

	// ajax->父组件(在父组件中定义新数据)->通过属性形式传给子组件->子组件接收(固定类型)
</script>

<style>

</style>
