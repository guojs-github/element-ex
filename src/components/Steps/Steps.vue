<template>
    <div class='test-item steps'>
		<div class='title'>Steps</div>
		
		<div class='row'>
			<el-button style='margin-top: 5px;' @click='onClickNext'>下一步</el-button>
		</div>

		<div class='row'>
			<el-steps :active='activeStep' finish-status='success' align-center>
				<el-step title='开始' description='创建领用申请单后处于这个状态' icon='el-icon-edit'></el-step>
				<el-step title='处理中...' description='提交领用申请单，等待领导审批' icon='el-icon-upload'></el-step>
				<el-step title='完毕' description='领导审批完毕'></el-step>
			</el-steps>			

			<el-steps :active='activeStep' finish-status='success' simple>
				<el-step title='开始' description='创建领用申请单后处于这个状态' icon='el-icon-edit'></el-step>
				<el-step title='处理中...' description='提交领用申请单，等待领导审批' icon='el-icon-upload'></el-step>
				<el-step title='完毕' description='领导审批完毕'></el-step>
			</el-steps>			
		</div>

		<div class='row'>
			<el-steps :active='activeStep' finish-status='success' align-center direction='vertical'>
				<el-step title='开始' description='创建领用申请单后处于这个状态' icon='el-icon-edit'></el-step>
				<el-step title='处理中...' description='提交领用申请单，等待领导审批' icon='el-icon-upload'></el-step>
				<el-step title='完毕' description='领导审批完毕'></el-step>
			</el-steps>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Steps',
		
		data () {
			return {
				activeStep: 0
			}		
		},
		
		methods: {			
			onClickNext (e) {
				console.log('On click next button')
				
				this.activeStep = ++this.activeStep % 4
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Steps.less' lang='less'/>
<style scoped>
</style>
