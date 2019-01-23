<template>
    <div class='test-item color-picker'>
		<div class='title'>Color Picker</div>
		
		<div class='row'>
			<el-color-picker
				v-model="color"
				show-alpha
				:predefine="predefineColors"
				size='mini'

				@change='onChange'>
			</el-color-picker>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'ColorPicker',
		
		data () {
			return {
				color: 'rgba(255, 69, 0, 0.68)',
				predefineColors: [
					'#ff4500',
					'#ff8c00',
					'#ffd700',
					'#90ee90',
					'#00ced1',
					'#1e90ff',
					'#c71585',
					'rgba(255, 69, 0, 0.68)',
					'rgb(255, 120, 0)',
					'hsv(51, 100, 98)',
					'hsva(120, 40, 94, 0.5)',
					'hsl(181, 100%, 37%)',
					'hsla(209, 100%, 56%, 0.73)',
					'#c7158577'
				]
			}		
		},
		
		methods: {
			onChange (value) {
				console.log('Color changed')
				console.log(value)
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./ColorPicker.less' lang='less'/>
<style scoped>
</style>
