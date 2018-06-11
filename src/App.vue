<template>
  <div id="app">
	<keep-alive>
    	<router-view/>
	</keep-alive>
	<!-- 路由中的内容加载过一次之后就放入内存之中,无需再次渲染 -->
    <!-- 当前显示内容是路由对应组件 -->
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
