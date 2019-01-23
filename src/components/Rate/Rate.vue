<template>
    <div class='test-item rate'>
		<div class='title'>Rate</div>
		
		<div class='row'>
			<el-rate
				v-model='value'
				show-text
				:colors='["#99A9BF", "#F7BA2A", "#FF9900"]'
				@change='onChange'>
			</el-rate>

			<el-rate
				v-model='value2'
				:icon-classes='["el-icon-error", "el-icon-info", "el-icon-success"]'
				void-icon-class='el-icon-question'
				:colors='["lightgray", "#F7BA2A", "green"]'>
			</el-rate>
		
			<el-rate
				v-model='value3'
				disabled
				show-score
				text-color='#ff9900'
				score-template="{value}">
			</el-rate>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Rate',
		
		data () {
			return {
				value: 3.2,
				value2: 2.57,
				value3: 4.56
			}		
		},
		
		methods: {
			onChange (value) {
				console.log('On change score')
				console.log(value)
			}
			/**********************/
	  }
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Rate.less' lang='less'/>
<style scoped>
</style>
