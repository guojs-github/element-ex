<template>
    <div class='test-item container'>
		<div class='title'>Container</div>
		
		<el-container style="height: 700px; border: 1px solid #eee"> <!--外围容器-->
		
			<el-aside width="200px" style="background-color: rgb(238, 241, 246)"> <!--侧边栏-->
				<el-menu :default-openeds="['1', '3']"><!--此处设置子菜单中默认展开的菜单，所谓'1'，'3'与下方el-sumenu index值一直-->

					<el-submenu index="1"><!--子菜单1-->
						<template slot="title"><i class="el-icon-message"></i>导航一</template>
						<el-menu-item-group>
							<template slot="title">分组一</template>
							<el-menu-item index="1-1">选项1</el-menu-item>
							<el-menu-item index="1-2">选项2</el-menu-item>
						</el-menu-item-group>
						<el-menu-item-group title="分组2">
							<el-menu-item index="1-3">选项3</el-menu-item>
						</el-menu-item-group>
						<el-submenu index="1-4">
							<template slot="title">选项4</template>
							<el-menu-item index="1-4-1">选项4-1</el-menu-item>
						</el-submenu>
					</el-submenu>
					
					<el-submenu index="2"><!--子菜单2-->
						<template slot="title"><i class="el-icon-menu"></i>导航二</template>
						<el-menu-item-group>
							<template slot="title">分组一</template>
							<el-menu-item index="2-1">选项1</el-menu-item>
							<el-menu-item index="2-2">选项2</el-menu-item>
						</el-menu-item-group>
						<el-menu-item-group title="分组2">
							<el-menu-item index="2-3">选项3</el-menu-item>
						</el-menu-item-group>
						<el-submenu index="2-4">
							<template slot="title">选项4</template>
							<el-menu-item index="2-4-1">选项4-1</el-menu-item>
						</el-submenu>
					</el-submenu>
					
					<el-submenu index="3"><!--子菜单3-->
						<template slot="title"><i class="el-icon-setting"></i>导航三</template>
						<el-menu-item-group>
							<template slot="title">分组一</template>
							<el-menu-item index="3-1">选项1</el-menu-item>
							<el-menu-item index="3-2">选项2</el-menu-item>
						</el-menu-item-group>
						<el-menu-item-group title="分组2">
							<el-menu-item index="3-3">选项3</el-menu-item>
						</el-menu-item-group>
						<el-submenu index="3-4">
							<template slot="title">选项4</template>
							<el-menu-item index="3-4-1">选项4-1</el-menu-item>
						</el-submenu>
					</el-submenu>

				</el-menu><!--菜单树容器-->
			</el-aside><!--侧边栏-->
		  
			<el-container><!--右侧内容容器-->
				<el-header style="text-align: right; font-size: 12px">
					<el-dropdown><!--下拉控件，与图标整合在一起-->
					<i class="el-icon-setting" style="margin-right: 15px"></i><!--右侧显示图标一个-->
						<el-dropdown-menu slot="dropdown"><!--此处为下拉控件-->
							<el-dropdown-item>查看</el-dropdown-item>
							<el-dropdown-item>新增</el-dropdown-item>
							<el-dropdown-item>删除</el-dropdown-item>
						</el-dropdown-menu>
					</el-dropdown>
					<span>王小虎</span>
				</el-header>
			
				<el-main><!--主数据显示部分-->
					<el-table :data="tableData"><!--绑定需要显示的数据源-->
						<el-table-column prop="date" label="日期" width="140"> <!--设置单头显示-->
						</el-table-column>
						<el-table-column prop="name" label="姓名" width="120">
						</el-table-column>
						<el-table-column prop="address" label="地址">
						</el-table-column>
					</el-table>
				</el-main>
				
				<el-footer>
					CopyRight 2018-2019
				</el-footer>
				
			</el-container><!--右侧内容容器-->
		 
		</el-container><!--外围容器-->		
    </div>
</template>

<script>
export default {
	name: 'Container',
	
	data () {
		const item = {
			date: '2016-05-02',
			name: '王小虎',
			address: '上海市普陀区金沙江路 1518 弄'
		}
		return {
			tableData: Array(20).fill(item)
		}		
	},
	
	methods: {
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Container.less' lang='less'/>
<style scoped>
</style>
