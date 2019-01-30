<template>
    <div class='test-item alert'>
		<div class='title'>Alert</div>
		
		<div class='row'>
			<el-alert class='hint' title='成功提示的文案' type='success' show-icon @close='onCloseHint'>
			</el-alert>
			<el-alert class='hint' title='消息提示的文案' type='info' show-icon @close='onCloseHint'>
			</el-alert>
			<el-alert class='hint' title='警告提示的文案' type='warning' show-icon center @close='onCloseHint'>
			</el-alert>
			<el-alert class='hint' title='错误提示的文案' type='error' :closable='false' show-icon description='文字说明文字说明文字说明文字说明文字说明文字说明'>
			</el-alert>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Alert',
		
		data () {
			return {
			}		
		},
		
		methods: {
			onCloseHint () {
				alert('On close hint')
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Alert.less' lang='less'/>
<style scoped>
</style>
