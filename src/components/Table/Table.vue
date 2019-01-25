<template>
    <div class='test-item table'>
		<div class='title'>Table</div>
		
		<div class='row'>
			<el-button @click='resetDateFilter'>清除日期过滤器</el-button>
			<el-button @click='clearFilter'>清除所有过滤器</el-button>
			<el-table
				:data='tableData'
				ref='table'
				style='width: 100%'
				height='250px'
				stripe
				border
				:row-class-name='tableRowClassName'
				show-summary
				sum-text='累计'
				:summary-method='getSummaries'
				:span-method='spanMethod'>				
				<el-table-column
					type='selection'
					width='80'
					fixed>
				</el-table-column>
				<el-table-column
					type='index'
					:index = 'indexMethod'
					width='50'
					fixed>
				</el-table-column>
				<el-table-column
					prop='date'
					label='日期'
					sortable
					width='180'
					fixed					
					column-key='date'
					:filters='[{text: "2016-05-01", value: "2016-05-01"}, {text: "2016-05-02", value: "2016-05-02"}, {text: "2016-05-03", value: "2016-05-03"}, {text: "2016-05-04", value: "2016-05-04"}]'
					:filter-method='filterDate'>
				</el-table-column>
				<el-table-column
					prop='name'
					label='姓名'
					width='180'>
				</el-table-column>
				<el-table-column
					prop='age'
					label='年龄'
					width='100'>
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
					label='地址'
					:formatter='formatAddress'>
				</el-table-column>
				<el-table-column
					prop='zip'
					label='邮编'
					width='120'>
				</el-table-column>
				<el-table-column
					prop='tag'
					label='标签'
					width='100'
					:filters='[{ text: "家", value: "家" }, { text: "公司", value: "公司" }]'
					:filter-method='filterTag'
					filter-placement='bottom-end'>
					<template slot-scope='scope'>
						<el-tag
							:type='scope.row.tag === "家" ? "primary" : "success"'
							disable-transitions>
							{{scope.row.tag}}
						</el-tag>
					</template>
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
			<div style='margin-top: 20px'>
				<el-button @click='toggleSelection([tableData[1], tableData[2]])'>切换第二、第三行的选中状态</el-button>
				<el-button @click='toggleSelection()'>取消选择</el-button>
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

		<div class='row'>		
			<el-table
				:data='tableData2'
				style='width: 100%'>
				<el-table-column type='expand'>
					<template slot-scope='props'>
						<el-form label-position='left' inline class='table-expand'>
							<el-form-item>
								<span class='label'>商品名称</span>
								<span class='value'>{{ props.row.name }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>所属店铺</span>
								<span class='value'>{{ props.row.shop }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>商品 ID</span>
								<span class='value'>{{ props.row.id }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>店铺 ID</span>
								<span class='value'>{{ props.row.shopId }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>商品分类</span>
								<span class='value'>{{ props.row.category }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>店铺地址</span>
								<span class='value'>{{ props.row.address }}</span>
							</el-form-item>
							<el-form-item>
								<span class='label'>商品描述</span>
								<span class='value'>{{ props.row.desc }}</span>
							</el-form-item>
						</el-form>
					</template>
				</el-table-column>
				<el-table-column
					label='商品 ID'
					prop='id'>
				</el-table-column>
				<el-table-column
					label='商品名称'
					prop='name'>
				</el-table-column>
				<el-table-column
					label='描述'
					prop='desc'>
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
					age: 19,
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333,
					tag: '家'
				}, {
					date: '2016-05-02',
					name: '王小虎',
					age: 19,
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333,
					tag: '公司'
				}, {
					date: '2016-05-04',
					name: '王小虎',
					age: 19,
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333,
					tag: '家'
				}, {
					date: '2016-05-01',
					name: '王小虎',
					age: 19,
					province: '上海',
					city: '普陀区',
					address: '上海市普陀区金沙江路 1518 弄',
					zip: 200333,
					tag: '公司'
				}],
				tableData2: [{
					id: '12987122',
					name: '好滋好味鸡蛋仔',
					category: '江浙小吃、小吃零食',
					desc: '荷兰优质淡奶，奶香浓而不腻',
					address: '上海市普陀区真北路',
					shop: '王小虎夫妻店',
					shopId: '10333'
				}, {
					id: '12987123',
					name: '好滋好味鸡蛋仔',
					category: '江浙小吃、小吃零食',
					desc: '荷兰优质淡奶，奶香浓而不腻',
					address: '上海市普陀区真北路',
					shop: '王小虎夫妻店',
					shopId: '10333'
				}, {
					id: '12987125',
					name: '好滋好味鸡蛋仔',
					category: '江浙小吃、小吃零食',
					desc: '荷兰优质淡奶，奶香浓而不腻',
					address: '上海市普陀区真北路',
					shop: '王小虎夫妻店',
					shopId: '10333'
				}, {
					id: '12987126',
					name: '好滋好味鸡蛋仔',
					category: '江浙小吃、小吃零食',
					desc: '荷兰优质淡奶，奶香浓而不腻',
					address: '上海市普陀区真北路',
					shop: '王小虎夫妻店',
					shopId: '10333'
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
			},

			resetDateFilter () {
				this.$refs.table.clearFilter('date')
			},

			clearFilter () {
				this.$refs.table.clearFilter()
			},
	  
			filterDate (value, row, column) {
				const property = column['property']
				return row[property] === value
			},

			filterTag (value, row, column) {
				return row.tag === value
			},	

			formatAddress (row, column) {
				return row.address + '!!!'
			},
			
			getSummaries (param) {
				const { columns, data } = param			
				const sums = [columns.length]
				
				for (let i = 0; i < sums.length; i++) {
					sums[i] = ''
				}
				sums[0] = '累计行'
				
				let ageTotal = 0
				data.forEach((row, index) => {
					ageTotal += row.age
				}) 
				let ageIndex = 1
				columns.forEach((column, index) => {
					if (column.property === 'age') {
						ageIndex = index
					}
				}) 
				
				sums[ageIndex] = ageTotal
				
				return sums
			},
			
			spanMethod ({row, column, rowIndex, columnIndex}) {
				if (rowIndex === 0) {
					if (columnIndex === 2) {
						return [2, 2] // 第一个参数为行数，第二个参数为列数
					} else if (columnIndex === 3) {
						return [0, 0]
					}
				}				
			},

			indexMethod (index) {
				return index * 3
			}			
		}
	}
</script>

<!-- Add 'scoped' attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Table.less' lang='less'/>
<style scoped>
</style>
