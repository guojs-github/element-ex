<template>
    <div class='test-item radio'>
		<div class='title'>Radio</div>
		
		<div class='row'>
			<el-radio-group v-model="radio1">
				<el-radio :label="1">备选项</el-radio>
				<el-radio :label="2">备选项</el-radio>
				<el-radio :label="3">备选项</el-radio>
			</el-radio-group>
		</div>

		<div class='row'>
			<el-radio-group v-model="radio2" size="small">
				<el-radio-button label="上海"></el-radio-button>
				<el-radio-button label="北京" disabled ></el-radio-button>
				<el-radio-button label="广州"></el-radio-button>
				<el-radio-button label="深圳"></el-radio-button>
			</el-radio-group>
		</div>

		<div class='row'>
			<el-radio-group v-model="radio3" size="small">
				<el-radio label="op1" border>备选项1</el-radio>
				<el-radio label="op2" border disabled>备选项2</el-radio>
			</el-radio-group>		
		</div>

	</div>
</template>

<script>
	export default {
		name: 'Radio',
		
		data () {
			return {
				radio1: 3,
				radio2: '广州',
				radio3: 'op2'
			}		
		},
		
		methods: {
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Radio.less' lang='less'/>
<style scoped>
</style>
