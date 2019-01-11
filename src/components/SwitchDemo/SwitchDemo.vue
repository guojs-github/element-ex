<template>
    <div class='test-item switch-demo'>
		<div class='title'>Switch</div>
		
		<div class='row'>
			<el-switch
				v-model="value"
				active-color="#13ce66"
				active-text='付钱'
				active-value='100'
				inactive-color="lightgray"
				inactive-text='不付'
				inactive-value='0'
				@change='onChange'>
			</el-switch>
		</div>

		<div class='row'>
			<el-switch
				v-model="value"
				active-value='100'
				inactive-value='0'
				disabled>
			</el-switch>
		</div>
	
	</div>
</template>

<script>
	export default {
		name: 'SwitchDemo',
		
		data () {
			return {
				value: '100'
			}		
		},
		
		methods: {
			onChange (value) {
				console.log('value:' + value)
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./SwitchDemo.less' lang='less'/>
<style scoped>
</style>
