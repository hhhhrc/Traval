<template>
	<ul class="list">
		<a class="item" 
		v-for="item of letters" 
		:key="item"
		:ref="item"
		@click="handleLetterClick"
		@touchstart.prevent="handleTouchStart"
		@touchmove="handleTouchMove"
		@touchend="handleTouchEnd"
		>
		{{item}}
		</a>
	</ul>
</template>

<script>
	export default{
		name:"CityAlhabet",
		props:{
			cities: Object
		},
		computed:{
			letters(){
				const letters=[]
				for(let i in this.cities){
					letters.push(i)
				}
				return letters
			}
		},
		data () {
			return{
				touchStatus:false,
				startY: 0,
				timer: null
			}
		},
		mounted (){
			this.startY = this.$refs['A'][0].offsetTop
				// A距离上面框的距离
		},
		// 数据发生变化时被执行(提高性能)
		methods:{
			handleLetterClick(e){
			this.$emit('change',e.target.innerText)
			},
			handleTouchStart(){
				this.touchStatus=true
			},
			handleTouchMove(e){
				if(this.touchStatus){
					if(this.timer){
						clearTimeout(this.timer)
					}
					this.timer=setTimeout(()=>{
						const touchY = e.touches[0].clientY-79
						// 距离顶部距离
						const index = Math.floor((touchY-this.startY)/20)
						// (点击处到框的距离-A到框的距离)/字母高度=下标
						if(index>=0&&index<this.letters.length){
							this.$emit('change',this.letters[index])
						}
					},5)
					// 函数节流:让函数过16毫秒再执行,中间如果滚动了,清除上一次执行这一次
					// 降低函数执行频率,提高性能
				}
			},
			handleTouchEnd(){
				this.touchStatus=true

			}


		}
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.list
	position:absolute
	display: flex
	flex-direction: column
	justify-content: center
	top:1.58rem
	right:0
	bottom:0
	width: .4rem
	.item
		line-height: .4rem
		text-align: center		
		color: $bgColor
</style>

