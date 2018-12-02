<template>
<!--  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
		
  </div> -->
	<index></index>
</template>

<script>
	
	import index from './views/index.vue'
	
	export default{
		components:{
			index
		}
	}
	
</script>

<style>

</style>
