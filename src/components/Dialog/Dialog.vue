<template>
    <div class='test-item dialog'>
		<div class='title'>Dialog</div>
		
		<div class='row'>
			<el-button type='text' @click='visible = true'>打开对话框</el-button>		
			<el-button type='text' @click='tableVisible = true'>打开表格对话框</el-button>		
			<el-button type='text' @click='formVisible = true'>打开表单对话框</el-button>		
		</div>
		
		<el-dialog 
			title='外层 Dialog' 
			:visible.sync='visible'
			:before-close='onCloseDialog'>
			<el-dialog
				width='30%'
				title='内层 Dialog'
				:visible.sync='innerVisible'
				append-to-body
				center>
			</el-dialog>
			<div 
				slot='footer' class='dialog-footer'>
				<el-button @click='visible = false'>取 消</el-button>
				<el-button type='primary' @click='innerVisible = true'>打开内层 Dialog</el-button>
			</div>
		</el-dialog>		

		<el-dialog title='收货地址' :visible.sync='tableVisible'>
			<el-table :data='tableData'>
				<el-table-column property='date' label='日期' width='150'></el-table-column>
				<el-table-column property='name' label='姓名' width='200'></el-table-column>
				<el-table-column property='address' label='地址'></el-table-column>
			</el-table>
		</el-dialog>

		<el-dialog title='收货地址' :visible.sync='formVisible'>
			<el-form :model='formData'>
				<el-form-item label='活动名称' :label-width='formLabelWidth'>
					<el-input v-model='formData.name' autocomplete='off'></el-input>
				</el-form-item>
				<el-form-item label='活动区域' :label-width='formLabelWidth'>
					<el-select v-model='formData.region' placeholder='请选择活动区域'>
						<el-option label='区域一' value='shanghai'></el-option>
						<el-option label='区域二' value='beijing'></el-option>
					</el-select>
				</el-form-item>
			</el-form>
			<div slot='footer' class='dialog-footer'>
				<el-button @click='formVisible = false'>取 消</el-button>
				<el-button type='primary' @click='formVisible = false'>确 定</el-button>
			</div>
		</el-dialog>		
	</div>
</template>

<script>
	export default {
		name: 'Dialog',
		
		data () {
			return {
				visible: false,
				innerVisible: false,
				tableVisible: false,
				tableData: [{
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
				formVisible: false,
				formData: {
					name: '',
					region: '',
					date1: '',
					date2: '',
					delivery: false,
					type: [],
					resource: '',
					desc: ''
				},
				formLabelWidth: '120px'				
			}		
		},
		
		methods: {
			onCloseDialog (done) {
				console.log('On close dialog')

				this.$confirm('确认关闭？')
					.then(_ => {
						done()
					})
					.catch(_ => {
					})				
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Dialog.less' lang='less'/>
<style scoped>
</style>
