<template>
    <div class='test-item slider'>
		<div class='title'>Slider</div>
		
		<div class='row'>
			<el-slider v-model='value' :format-tooltip='formatTooltip'></el-slider>
		</div>

		<div class='row'>
			<el-slider v-model='value2' :step='5' show-stops></el-slider>
		</div>

		<div class='row'>
			<el-slider v-model='value3' show-input></el-slider>
		</div>

		<div class='row'>
			<el-slider v-model='value4' :min='3' :max='12' range :step='1' show-stops ></el-slider>
		</div>

		<div class='row'>
			<el-slider v-model='value5' vertical height='100px'></el-slider>
		</div>

	</div>
</template>

<script>
	export default {
		name: 'Slider',
		
		data () {
			return {
				value: 10,
				value2: 20,
				value3: 30,
				value4: [4, 6],
				value5: 50
			}		
		},
		
		methods: {
			/**********************/
			formatTooltip (val) {
				return val / 10
			}
	  }
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Slider.less' lang='less'/>
<style scoped>
</style>
