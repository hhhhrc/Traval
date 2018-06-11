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
	import {mapState} from 'vuex'
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
				lastCity:'',
				swiperList: [],
				iconList:[],
				recommendList:[],
				weekendList:[]
			}
	},
	computed:{
		...mapState(['city'])
	},
	methods:{
		getHomeInfo () {
			axios.get('/api/index.json?city=' + this.city)
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
		this.lastCity=this.city
		this.getHomeInfo( )
	},
	activated(){
		if(this.lastCity !== this.city){
			this.lastCity=this.city
			this.getHomeInfo()
		}
	}
	// keepalive新增的生命周期函数,页面重新加载时执行.
	}

	// ajax->父组件(在父组件中定义新数据)->通过属性形式传给子组件->子组件接收(固定类型)
</script>

<style>

</style>
