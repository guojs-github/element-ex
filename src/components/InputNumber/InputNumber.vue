<template>
    <div class='test-item input-number'>
		<div class='title'>Input Number</div>
		
		<div class='row'>
			<el-input-number v-model="num1" :precision="2" :step="0.1" :max="10"></el-input-number>
			<el-input-number v-model="num1" :precision="2" :step="0.1" :max="10" controls-position='right'></el-input-number>
		</div>		
	</div>
</template>

<script>
	export default {
		name: 'InputNumber',
		
		data () {
			return {
				num1: 1
			}		
		},
		
		methods: {		
		
			/*****************************/
			
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./InputNumber.less' lang='less'/>
<style scoped>
</style>
