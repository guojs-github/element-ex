<template>
    <div class='test-item tooltip'>
		<div class='title'>Tooltip</div>
		
		<div class='box'>
			<div class='top'>
				<el-tooltip 
					class='item' 
					effect='dark' 
					content='Top Left 提示文字' 
					placement='top-start'>
					<el-button>上左</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='dark' 
					placement='top'>
					<div slot='content'>多行信息<br/>第二行信息</div>
					<el-button>上边 多行信息</el-button>
				</el-tooltip>
				<el-tooltip 
					:disabled='disabled'
					class='item' 
					effect='dark' 
					content='Top Right 提示文字' 
					placement='top-end'>
					<el-button @click='disabled = !disabled'>上右 点击{{disabled? '开启': '关闭' }}</el-button>
				</el-tooltip>
			</div>

			<div class='left'>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Left Top 提示文字' 
					placement='left-start'>
					<el-button>左上</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Left Center 提示文字' 
					placement='left'>
					<el-button>左边</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Left Bottom 提示文字' 
					placement='left-end'>
					<el-button>左下</el-button>
				</el-tooltip>
			</div>

			<div class='right'>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Right Top 提示文字' 
					placement='right-start'>
					<el-button>右上</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Right Center 提示文字' 
					placement='right'>
					<el-button>右边</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='light' 
					content='Right Bottom 提示文字' 
					placement='right-end'>
					<el-button>右下</el-button>
				</el-tooltip>
			</div>

			<div class='bottom'>
				<el-tooltip 
					class='item' 
					effect='dark' 
					content='Bottom Left 提示文字' 
					placement='bottom-start'>
					<el-button>下左</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='dark' 
					content='Bottom Center 提示文字' 
					placement='bottom'>
					<el-button>下边</el-button>
				</el-tooltip>
				<el-tooltip 
					class='item' 
					effect='dark' 
					content='Bottom Right 提示文字' 
					placement='bottom-end'>
					<el-button>下右</el-button>
				</el-tooltip>
			</div>
		</div>
	</div>
</template>

<script>
	export default { 
		name: 'Tooltip',
		
		data () {
			return {
				disabled: false
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Tooltip.less' lang='less'/>
<style scoped>
</style>
