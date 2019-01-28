<template>
    <div class='test-item progress'>
		<div class='title'>Progress</div>
		
		<div class='row'>
			<el-progress :percentage="0"></el-progress>
			<el-progress :percentage="70"></el-progress>
			<el-progress :text-inside='true' :stroke-width=strokeWidth18 :percentage="80" color="#8e71c7"></el-progress>
			<el-progress :text-inside='true' :stroke-width=strokeWidth24 :percentage="100" status="success"></el-progress>
			<el-progress type='circle' :text-inside='true' :stroke-width=strokeWidth32 :percentage="50" status="exception"></el-progress>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Progress',
		
		data () {
			return {
				strokeWidth18: 18,
				strokeWidth24: 24,
				strokeWidth32: 32
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Progress.less' lang='less'/>
<style scoped>
</style>
