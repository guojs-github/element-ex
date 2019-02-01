<template>
    <div class='test-item notification'>
		<div class='title'>Notification</div>
		
		<div class='row'>
			<el-button plain @click="onClickSuccess"> 成功 </el-button>
			<el-button plain @click="onClickWarning"> 警告 </el-button>
			<el-button plain @click="onClickInfo"> 消息 </el-button>
			<el-button plain @click="onClickError"> 错误 </el-button>		
			<el-button plain @click="onClickHTML"> 自定义消息 </el-button>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Notification',
		
		data () {
			return {
			}		
		},
		
		methods: {
			onClickSuccess (e) {
				this.$notify({
					title: '成功',
					message: '这是一条成功的提示消息',
					type: 'success',
					duration: 0
				})		
			},
			
			onClickWarning (e) {
				this.$notify({
					title: '警告',
					message: '这是一条警告的提示消息',
					type: 'warning',
					position: 'bottom-right'
				})		
			},
			
			onClickInfo (e) {
				this.$notify({
					title: '提示',
					message: '这是一条普通的提示消息',
					position: 'bottom-left'
				})		
			},
			
			onClickError (e) {
				this.$notify({
					title: '错误',
					message: '这是一条错误的提示消息',
					type: 'error',
					position: 'top-left'
				})		
			},

			onClickHTML (e) {
				this.$notify({
					title: 'HTML',
					message: '这是一条<span style="font-size: 30px; font-weight: bold; color: red;">HTML</span>的提示消息',
					dangerouslyUseHTMLString: true,
					offset: 100,
					showClose: false
				})		
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Notification.less' lang='less'/>
<style scoped>
</style>
