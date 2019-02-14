<template>
    <div class='test-item popover'>
		<div class='title'>Popover</div>
		
		<div class='row'>
			<el-popover
				placement='top-start'
				title='标题'
				width='200'
				trigger='hover'
				content='这是一段内容,这是一段内容,这是一段内容,这是一段内容。'>
				<el-button slot='reference'>hover 激活</el-button>
			</el-popover>

			<el-popover
				v-model='visible2'
				placement='bottom'
				width='200'
				trigger='click'>
				<p>这是一段内容这是一段内容确定删除吗？</p>
				<div style='text-align: right; margin: 0'>
					<el-button size='mini' type='text' @click='visible2 = false'>取消</el-button>
					<el-button type='primary' size='mini' @click='visible2 = false'>确定</el-button>
				</div>
				<el-button slot='reference'>click 激活</el-button>
			</el-popover>

			<el-popover
				placement='right'
				title='标题'
				width='auto'
				trigger='focus'
				content='这是一段内容,这是一段内容,这是一段内容,这是一段内容。'>
				<el-table :data='gridData' >
					<el-table-column width='150' property='date' label='日期'></el-table-column>
					<el-table-column width='100' property='name' label='姓名'></el-table-column>
					<el-table-column width='300' property='address' label='地址'></el-table-column>
				</el-table>
				<el-button slot='reference'>focus 激活</el-button>
			</el-popover>

			<el-popover
				placement='bottom'
				title='标题'
				width='200'
				trigger='manual'
				content='这是一段内容,这是一段内容,这是一段内容,这是一段内容。'
				v-model='visible'>
				<el-button slot='reference' @click='visible = !visible'>手动{{ visible? '关闭': '激活' }}</el-button>
			</el-popover>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Popover',
		
		data () {
			return {
				visible: false,
				gridData: [{
					date: '2016-05-02',
					name: '王小虎',
					address: '上海市普陀区金沙江路 1518 弄'
				}, {
					date: '2016-05-04',
					name: '王小虎',
					address: '上海市普陀区金沙江路 1518 弄'
				}, {
					date: '2016-05-01',
					name: '王小虎',
					address: '上海市普陀区金沙江路 1518 弄'
				}, {
					date: '2016-05-03',
					name: '王小虎',
					address: '上海市普陀区金沙江路 1518 弄'
				}],
				visible2: false
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Popover.less' lang='less'/>
<style scoped>
</style>
