<template>
    <div class='test-item input'>
		<div class='title'>Input</div>
		
		<div class='row'>
			<el-input v-model="input1" placeholder="请选择日期" suffix-icon="el-icon-date" clearable/>		
			<el-input v-model="input2" placeholder="请输入关键字" clearable>
				<i slot='prefix' class='el-input__icon el-icon-search'/>
			</el-input>		
			<el-input v-model="input3" placeholder="请输入信息" :disabled='true'/>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Input',
		
		data () {
			return {
				input1: '2019-01-01',
				input2: '',
				input3: ''
			}		
		},
		
		methods: {
			/*****************************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Input.less' lang='less'/>
<style scoped>
</style>
