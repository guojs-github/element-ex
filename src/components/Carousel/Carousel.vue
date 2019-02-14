<template>
    <div class='test-item carousel'>
		<div class='title'>Carousel</div>
		
		<div class='row'>
			<el-carousel height='150px'>
				<el-carousel-item v-for='item in 4' :key='item'>
					<h3>{{ item }}</h3>
				</el-carousel-item>
			</el-carousel>		

			<el-carousel 
				height='150px' 
				trigger='click'
				indicator-position='outside'
				arrow='always'>
				<el-carousel-item v-for='item in 4' :key='item'>
					<h3>{{ item }}</h3>
				</el-carousel-item>
			</el-carousel>		

			<el-carousel 
				height='150px' 
				interval = '5000'
				indicator-position='outside'
				type='card'>
				<el-carousel-item v-for='item in 4' :key='item'>
					<h3>{{ item }}</h3>
				</el-carousel-item>
			</el-carousel>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Carousel',
		
		data () {
			return {
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Carousel.less' lang='less'/>
<style scoped>
</style>
