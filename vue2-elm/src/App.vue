<template>
	<div>
		<transition name="router-fade" mode="out-in">
			<keep-alive> 
			    <router-view v-if="$route.meta.keepAlive"></router-view>   //这里是会被缓存的视图组件
			</keep-alive>
    	</transition>
    	<transition name="router-fade" mode="out-in">
			<router-view v-if="!$route.meta.keepAlive"></router-view>
		</transition>
    </div>
</template>
	// import svgIcon from './components/common/svg.vue';
<script>
  	export default {
    	components:{
			// svgIcon
		},
  	}

</script>

<style lang="scss">
  	@import './style/common';
	.router-fade-enter-active, .router-fade-leave-active {
	  	transition: opacity .3s;
	}
	.router-fade-enter, .router-fade-leave-active {
	  	opacity: 0;
	}
</style>
