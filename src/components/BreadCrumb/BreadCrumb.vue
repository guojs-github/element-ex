<template>
    <div class='test-item bread-crumb'>
		<div class='title'>Bread Crumb</div>
		
		<div class='row'>
			<el-breadcrumb separator='/'>
				<el-breadcrumb-item :to='{ path: "/" }'>首页</el-breadcrumb-item>
				<el-breadcrumb-item><a href='/'>活动管理</a></el-breadcrumb-item>
				<el-breadcrumb-item>活动列表</el-breadcrumb-item>
				<el-breadcrumb-item>活动详情</el-breadcrumb-item>
			</el-breadcrumb>		
		</div>

		<div class='row'>
			<el-breadcrumb separator-class='el-icon-arrow-right'>
				<el-breadcrumb-item :to='{ path: "/" }'>首页</el-breadcrumb-item>
				<el-breadcrumb-item><a href='/'>活动管理</a></el-breadcrumb-item>
				<el-breadcrumb-item>活动列表</el-breadcrumb-item>
				<el-breadcrumb-item>活动详情</el-breadcrumb-item>
			</el-breadcrumb>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'BreadCrumb',
		
		data () {
			return {
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./BreadCrumb.less' lang='less'/>
<style scoped>
</style>
