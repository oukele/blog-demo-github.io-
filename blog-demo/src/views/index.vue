<template>
	<div class="layout">
		<Sider :style="{position: 'fixed', height: '100vh', left: 0, overflow: 'auto'}">
			<Menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
				<Submenu name="1" class="la">
					<template slot="title">
						<Icon type="ios-navigate"></Icon>
						{{title_msg}}
					</template>
					<router-link to="/table">
						<MenuItem name="1-1"> 主 列 表 </MenuItem>
					</router-link>
					<router-link to="/test">
						<MenuItem name="1-2">点 一 下</MenuItem>
					</router-link>
					<router-link to="/about">
						<MenuItem name="1-3"> 关 于 </MenuItem>
					</router-link>
				</Submenu>
				<Submenu name="2">
					<template slot="title">
						<Icon type="ios-keypad"></Icon>
						待加入
					</template>
					<MenuItem name="2-1">Option 1</MenuItem>
					<MenuItem name="2-2">Option 2</MenuItem>
				</Submenu>
				<Submenu name="3">
					<template slot="title">
						<Icon type="ios-analytics"></Icon>
						待加入
					</template>
					<MenuItem name="3-1">Option 1</MenuItem>
					<MenuItem name="3-2">Option 2</MenuItem>
				</Submenu>
			</Menu>
		</Sider>
		<Layout :style="{marginLeft: '200px'}">
			<Header :style="{background: '#fff', boxShadow: '0 2px 3px 2px rgba(0,0,0,.1)'}">
				<marquee><img width="124px" height="64px" src="http://img0.ph.126.net/cAH2o5_UiEkTHPMweNSRaw==/6632402572817269737.gif"></marquee>

			</Header>
			<Content :style="{padding: '0 16px 16px'}">
				<Breadcrumb :style="{margin: '16px 0'}">
					<BreadcrumbItem>您当前所在的位置:</BreadcrumbItem>
					<BreadcrumbItem>{{title_msg}}</BreadcrumbItem>
					<BreadcrumbItem>{{top_msg}}</BreadcrumbItem>
				</Breadcrumb>
				<Card>
					<div style="height: 455px;margin: auto;">
						<router-view />
					</div>
				</Card>
			</Content>
		</Layout>
	</div>
</template>
<script>
	//import Home from './Home.vue'

	export default {
		components: {
			//Home
		},
		data() {
			return {
				title_msg: "主页",
				top_msg: ""
			}
		},
		methods: {
			take(e){
				this.top_msg = e;
			}
		},
		mounted() {

			let that = this;//关键的一步
			var x = document.querySelectorAll(".ivu-menu-item");
			for (var i = 0; i < x.length; i++) {
				x[i].addEventListener("click",function(){
					that.take(this.innerText);
				});
			}
		}
	}
</script>
<style scoped>
	.layout {
		border: 1px solid #d7dde4;
		background: #f5f7f9;
		position: relative;
		border-radius: 4px;
		overflow: hidden;
	}

	.layout-header-bar {
		background: #fff;
		box-shadow: 0 1px 1px rgba(0, 0, 0, .1);
	}
</style>
