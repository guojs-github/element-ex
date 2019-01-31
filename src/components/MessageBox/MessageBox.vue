<template>
    <div class='test-item message-box'>
		<div class='title'>Message box</div>
		
		<div class='row'>
			<el-button @click="onClickMessageBox">Message Box</el-button>
			<el-button @click="onClickConfirmBox">Confirm Box</el-button>
			<el-button @click="onClickInputBox">Input Box</el-button>
			<el-button @click="onClickCustomizedMessageBox">Customized Message Box</el-button>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'MessageBox',
		
		data () {
			return {
			}		
		},
		
		methods: {
			onClickMessageBox () {
				this.$alert(
					'这是一段内容', 
					'标题名称', 
					{
						confirmButtonText: '确定',
						callback: action => {
							this.$message({
								type: 'info',
								message: `action: ${action}`
							})
						}
					}
				)
			},
			
			onClickConfirmBox () {
				this.$confirm(
					'此操作将永久删除该文件, 是否继续?', 
					'提示', 
					{
						confirmButtonText: '确定',
						cancelButtonText: '取消',
						type: 'warning'
					}
				).then(() => {
					this.$message({
						type: 'success',
						message: '删除成功!'
					})					
				}).catch(() => {
					this.$message({
						type: 'info',
						message: '已取消操作'
					})					
				})
			},
			
			onClickInputBox () {
				this.$prompt(
					'请输入邮箱', 
					'提示', 
					{
						confirmButtonText: '确定',
						cancelButtonText: '取消',
						inputPattern: /[\w!#$%&'*+/=?^_`{|}~-]+(?:\.[\w!#$%&'*+/=?^_`{|}~-]+)*@(?:[\w](?:[\w-]*[\w])?\.)+[\w](?:[\w-]*[\w])?/,
						inputErrorMessage: '邮箱格式不正确'
					}
				).then(({ value }) => {
					this.$message({
						type: 'success',
						message: '你的邮箱是: ' + value
					})
				}).catch(() => {
					this.$message({
						type: 'info',
						message: '取消输入'
					})       
				})
			},
			
			onClickCustomizedMessageBox () {
				this.$alert(
					'<strong>这是 <i style="color: blue;font-size: 30px; opacity: 0.2">HTML</i> 片段</strong>', 
					'HTML 片段', 
					{
						dangerouslyUseHTMLString: true
					}
				)			
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./MessageBox.less' lang='less'/>
<style scoped>
</style>
