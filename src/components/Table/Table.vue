<template>
    <div class='test-item table'>
		<div class='title'>Table</div>
		
		<div class='row'>
			<el-table
				:data='tableData'
				ref='table'
				style='width: 100%'
				height='200px'
				stripe
				border
				:row-class-name="tableRowClassName">
				<el-table-column
					type='selection'
					width='50'
					fixed>
				</el-table-column>
				<el-table-column
					type='index'
					width='50'
					fixed>
				</el-table-column>
				<el-table-column
					prop='date'
					label='日期'
					sortable
					width='180'
					fixed>
				</el-table-column>
				<el-table-column
					prop='name'
					label='姓名'
					width='180'>
				</el-table-column>
				<el-table-column
					prop='province'
					label='省份'
					width='120'>
				</el-table-column>
				<el-table-column
					prop='city'
					label='市区'
					width='120'>
				</el-table-column>
				<el-table-column
					prop='address'
					show-overflow-tooltip
					label='地址'>
				</el-table-column>
				<el-table-column
					prop='zip'
					label='邮编'
					width='120'>
				</el-table-column>
				<el-table-column
					fixed='right'
					label='操作'
					width='100'>
					<template slot-scope='scope'>
						<el-button @click='onClickView(scope.row)' type='text' size='small'>查看</el-button>
						<el-button type='text' size='small'>编辑</el-button>
					</template>
				</el-table-column>
			</el-table>
			<div style="margin-top: 20px">
				<el-button @click="toggleSelection([tableData[1], tableData[2]])">切换第二、第三行的选中状态</el-button>
				<el-button @click="toggleSelection()">取消选择</el-button>
			</div>
		</div>
		
		<div class='row'>
			<el-table
				:data='tableData'
				style='width: 100%'>
				<el-table-column
					prop='date'
					label='日期'
					width='150'>
				</el-table-column>
				<el-table-column label='配送信息'>
					<el-table-column
						prop='name'
						label='姓名'
						width='120'>
					</el-table-column>
					<el-table-column label='地址'>
						<el-table-column
							prop='province'
							label='省份'
							width='120'>
						</el-table-column>
						<el-table-column
							prop='city'
							label='市区'
							width='120'>
						</el-table-column>
						<el-table-column
							prop='address'
							label='地址'
							width='300'>
						</el-table-column>
						<el-table-column
							prop='zip'
							label='邮编'
							width='120'>
						</el-table-column>
					</el-table-column>
				</el-table-column>
			</el-table>
		</div>		
	</div>
</template>

<script>
	export default {
		name: 'Table',
		
		data () {
			return {
				tableData: [{
					date: '2016-05-03',
					name: '王小虎',
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333				
				}, {
					date: '2016-05-02',
					name: '王小虎',
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333
				}, {
					date: '2016-05-04',
					name: '王小虎',
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333

				}, {
					date: '2016-05-01',
					name: '王小虎',
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333

				}]
			}		
		},
		
		methods: {
			/**********************/
			tableRowClassName ({row, rowIndex}) {
				if (rowIndex === 2) {
					return 'warning-row'
				} 
				return ''
			},

			toggleSelection (rows) {
				if (rows) {
					rows.forEach(row => {
						this.$refs.table.toggleRowSelection(row)
					})
				} else {
					this.$refs.table.clearSelection()
				}
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Table.less' lang='less'/>
<style scoped>
</style>
