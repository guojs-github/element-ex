<template>
    <div class='test-item message'>
		<div class='title'>Message</div>
		
		<div class='row'>
			<el-button :plain='true' @click='onClickInfo'>消息</el-button>
			<el-button :plain='true' @click='onClickSuccess'>成功</el-button>
			<el-button :plain='true' @click='onClickWarning'>警告</el-button>
			<el-button :plain='true' @click='onClickError'>错误</el-button>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Message',
		
		data () {
			return {
			}		
		},
		
		methods: {
			onClickInfo () {
				this.$message({
					message: '这是一条消息提示'
				})
			},

			onClickSuccess () {
				this.$message({
					message: '恭喜你，这是一条成功消息',
					type: 'success'
				})
			},

			onClickWarning () {
				this.$message({
					message: '警告哦，这是一条警告消息',
					type: 'warning',
					center: true,
					showClose: true
				})
			},

			onClickError () {
				this.$message({
					message: '<strong style="color:blue;">错了哦</strong>，<i>这是一条错误消息</i>',
					dangerouslyUseHTMLString: true,
					type: 'error',
					showClose: true
				})
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Message.less' lang='less'/>
<style scoped>
</style>
