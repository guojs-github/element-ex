<template>
    <div class='test-item card'>
		<div class='title'>Card</div>
		
		<div class='row'>
			<el-card class='box-card'>
				<div slot='header' class='clearfix'>
					<span>卡片名称</span>
					<el-button style='float: right; padding: 3px 0' type='text'>操作按钮</el-button>
				</div>
				<div v-for='o in 4' :key='o' class='text item'>
				{{'列表内容 ' + o }}
				</div>
			</el-card>		
		</div>
		
		<div class='row'>
			<el-card v-for='(o, index) in 2' :key='o'
				 class='box-card-1'
				 shadow='hover'>
				<img src='../../assets/image/hamburger.png' class='image'>
				<div style='padding: 14px;'>
					<span>好吃的汉堡</span>
					<div class='bottom clearfix'>
					<time class='time'>{{ currentDate }}</time>
					<el-button type='text' class='button'>操作按钮</el-button>
					</div>
				</div>
			</el-card>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Card',
		
		data () {
			return {
				currentDate: new Date()
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Card.less' lang='less'/>
<style scoped>
</style>
