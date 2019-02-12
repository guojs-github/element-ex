<template>
    <div class='test-item dropdown'>
		<div class='title'>Dropdown</div>
		
		<div class='row'>
			<el-dropdown @command='onCommand'>
				<span class='el-dropdown-link'>
					下拉菜单<i class='el-icon-arrow-down el-icon--right'></i>
				</span>
				<el-dropdown-menu slot='dropdown'>
					<el-dropdown-item command='1'>黄金糕</el-dropdown-item>
					<el-dropdown-item command='2'>狮子头</el-dropdown-item>
					<el-dropdown-item command='3'>螺蛳粉</el-dropdown-item>
					<el-dropdown-item command='4' disabled>双皮奶</el-dropdown-item>
					<el-dropdown-item command='5' divided>蚵仔煎</el-dropdown-item>
				</el-dropdown-menu>
			</el-dropdown>		

			<el-dropdown size='mini' trigger='click' :hide-on-click='false'>
				<span class='el-dropdown-link'>
					下拉菜单<i class='el-icon-arrow-down el-icon--right'></i>
				</span>
				<el-dropdown-menu slot='dropdown'>
					<el-dropdown-item>黄金糕</el-dropdown-item>
					<el-dropdown-item>狮子头</el-dropdown-item>
					<el-dropdown-item>螺蛳粉</el-dropdown-item>
					<el-dropdown-item>双皮奶</el-dropdown-item>
					<el-dropdown-item>蚵仔煎</el-dropdown-item>
				</el-dropdown-menu>
			</el-dropdown>
			
			<el-dropdown split-button type='primary'>
				下拉菜单
				<el-dropdown-menu slot='dropdown'>
					<el-dropdown-item>黄金糕</el-dropdown-item>
					<el-dropdown-item>狮子头</el-dropdown-item>
					<el-dropdown-item>螺蛳粉</el-dropdown-item>
					<el-dropdown-item>双皮奶</el-dropdown-item>
					<el-dropdown-item>蚵仔煎</el-dropdown-item>
				</el-dropdown-menu>
			</el-dropdown>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Dropdown',
		
		data () {
			return {
			}		
		},
		
		methods: {
			onCommand (command) {
				console.log('Command:' + command)
				this.$message('click on item ' + command)
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Dropdown.less' lang='less'/>
<style scoped>
</style>
