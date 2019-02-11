<template>
    <div class='test-item tab'>
		<div class='title'>Tab</div>
		
		<div class='row'>
			<el-radio-group v-model='tabPosition'>
				<el-radio-button label='top'>top</el-radio-button>
				<el-radio-button label='right'>right</el-radio-button>
				<el-radio-button label='bottom'>bottom</el-radio-button>
				<el-radio-button label='left'>left</el-radio-button>
			</el-radio-group>

			<el-tabs v-model='activeName' :tab-position='tabPosition' @tab-click='onClickTab'>
				<el-tab-pane label='用户管理' name='first'>用户管理</el-tab-pane>
				<el-tab-pane label='配置管理' name='second'>配置管理</el-tab-pane>
				<el-tab-pane label='角色管理' name='third'>角色管理</el-tab-pane>
				<el-tab-pane label='定时任务补偿' name='fourth'>定时任务补偿</el-tab-pane>
			</el-tabs>		
		</div>

		<div class='row'>
			<el-tabs v-model='activeName' type='card' @tab-click='onClickTab'>
				<el-tab-pane label='用户管理' name='first'>用户管理</el-tab-pane>
				<el-tab-pane label='配置管理' name='second'>配置管理</el-tab-pane>
				<el-tab-pane label='角色管理' name='third'>角色管理</el-tab-pane>
				<el-tab-pane label='定时任务补偿' name='fourth'>定时任务补偿</el-tab-pane>
			</el-tabs>		
		</div>

		<div class='row'>
			<el-tabs v-model='activeName' type='border-card' @tab-click='onClickTab'>
				<el-tab-pane label='用户管理' name='first'>用户管理</el-tab-pane>
				<el-tab-pane label='配置管理' name='second'>配置管理</el-tab-pane>
				<el-tab-pane label='角色管理' name='third'>角色管理</el-tab-pane>
				<el-tab-pane label='定时任务补偿' name='fourth'>定时任务补偿</el-tab-pane>
				<el-tab-pane name='fifth'>
					<span slot='label'>
						<i class='el-icon-date'></i> 我的行程
					</span>
					我的行程
				</el-tab-pane>
			</el-tabs>		
		</div>
		
		<div class='row'>
			<div>
			<el-button
				size='small'
				@click='addTab(editableTabsValue2)'>
				Add Tab
			</el-button>
			</div>
			<el-tabs
				v-model='editableTabsValue2' 
				type='card' 
				closable 
				@tab-remove='removeTab'>
				<el-tab-pane
					v-for='(item) in editableTabs2'
					:key='item.name'
					:label='item.title'
					:name='item.name'
				>
					{{item.content}}
				</el-tab-pane>
			</el-tabs>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Tab',
		
		data () {
			return {
				activeName: 'third',
				tabPosition: 'top',
				editableTabsValue2: '2',
				editableTabs2: [{
					title: 'Tab 1',
					name: '1',
					content: 'Tab 1 content'
				}, {
					title: 'Tab 2',
					name: '2',
					content: 'Tab 2 content'
				}],
				tabIndex: 2
			}
		},
		
		methods: {
			onClickTab (tab, event) {
				console.log(tab, event)
			},
			
			/**********************/
			addTab (targetName) {
				let newTabName = ++this.tabIndex + ''
				this.editableTabs2.push({
					title: 'New Tab',
					name: newTabName,
					content: 'New Tab content'
				})
				this.editableTabsValue2 = newTabName
			},
			
			removeTab (targetName) {
				let tabs = this.editableTabs2
				let activeName = this.editableTabsValue2
				if (activeName === targetName) {
					tabs.forEach((tab, index) => {
						if (tab.name === targetName) { // 需要修改选中的tab项
							let nextTab = tabs[index + 1] || tabs[index - 1] // 利用或运算的短路特性，如果后一项undefined，就返回前一项的值
							if (nextTab) {
								activeName = nextTab.name
							}
						}
					})
				}

				this.editableTabsValue2 = activeName
				this.editableTabs2 = tabs.filter(tab => tab.name !== targetName) // 设置过滤，过滤掉当前选中值，更改数组
			}			
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Tab.less' lang='less'/>
<style scoped>
</style>
