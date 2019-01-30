<template>
    <div class='test-item badge'>
		<div class='title'>Badge</div>
		
		<div class='row'>
			<el-badge :value='12' class='item'>
				<el-button size='small'>评论</el-button>
			</el-badge>
			<el-badge :value='300' :max='10' class='item'>
				<el-button size="small">回复</el-button>
			</el-badge>
			<el-badge is-dot class='item'>
				<el-button size="small">回复</el-button>
			</el-badge>
			<el-badge value='new' class='item' type='primary'>
				<el-button size='small'>评论</el-button>
			</el-badge>
			<el-badge :value='2' class='item' type='warning'>
				回复
			</el-badge>

			<el-dropdown class='dropdown-menu' trigger='click'>
				<span class='el-dropdown-link'>
					点我查看<i class='el-icon-caret-bottom el-icon--right'></i>
				</span>
				<el-dropdown-menu slot='dropdown'>
					<el-dropdown-item class='clearfix'>
						评论
						<el-badge class='mark' :value='12' />
					</el-dropdown-item>
					<el-dropdown-item class='clearfix'>
						回复
						<el-badge class='mark' :value='3' />
					</el-dropdown-item>
				</el-dropdown-menu>
			</el-dropdown>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Badge',
		
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
<style scoped src='./Badge.less' lang='less'/>
<style scoped>
</style>
