<template>
    <div class='test-item tree'>
		<div class='title'>Tree</div>
		
		<div class='row'>
			<el-input placeholder="输入关键字进行过滤" v-model="filterText">
			</el-input>

			<el-tree 
				ref='tree1'
				:data='data' 
				:props='props'
				node-key='id'
				accordion
				draggable
				show-checkbox
				:filter-node-method='filterNode'
				@node-click='onNodeClick'>
				<span class='custom-tree-node' slot-scope='{ node, data }'>
					<span>{{ node.label }}</span>
					<span>
						<el-button
							type="text"
							size="mini"
							@click="() => append(data)">
							添加
						</el-button>
						<el-button
							type="text"
							size="mini"
							@click="() => remove(node, data)">
							删除
						</el-button>
					</span>
				</span>				
			</el-tree>		
		</div>
		
		<div class='row'>		
			<el-tree
				:props='dynProps'
				:load='loadNodes'
				lazy
				show-checkbox
				@check-change="onCheckChange">
			</el-tree>		
		</div>
		
	</div>
</template>

<script>
	let id = 10000
	
	export default {
		name: 'Tree',
		
		data () {
			return {
				data: [{
					id: 1,
					label: '一级 1',
					children: [{
						id: 11,
						label: '二级 1-1',
						children: [{
							id: 111,
							label: '三级 1-1-1'
						}]
					}]
				}, {
					id: 2,
					label: '一级 2',
					children: [{
						id: 21,
						label: '二级 2-1',
						children: [{
							id: 211,
							label: '三级 2-1-1'
						}]
					}, {
						id: 22,
						label: '二级 2-2',
						children: [{
							id: 221,
							label: '三级 2-2-1'
						}]
					}]
				}, {
					id: 3,
					label: '一级 3',
					children: [{
						id: 31,
						label: '二级 3-1',
						children: [{
							id: 311,
							label: '三级 3-1-1'
						}]
					}, {
						id: 32,
						label: '二级 3-2',
						children: [{
							id: 321,
							label: '三级 3-2-1'
						}]
					}]
				}],
				props: {
					children: 'children',
					label: 'label'
				},
				filterText: '',
				dynProps: {
					label: 'name',
					children: 'zones'
				},
				count: 900
			}		
		},		
	
		methods: {
			onNodeClick (data) {
				console.log(data)
			},

			onCheckChange (data, checked, indeterminate) {
				console.log(data, checked, indeterminate)
			},			
			
			/**********************/
			filterNode (value, data) {
				if (!value) return true
				return data.label.indexOf(value) !== -1
			},		
			
			append (data) {
				const newChild = { 
					id: id++, 
					label: '测试项目', 
					children: []
				}
				
				if (!data.children) {
					this.$set(data, 'children', [])
				}
				
				data.children.push(newChild)
			},

			remove (node, data) {
				const parent = node.parent
				const children = parent.data.children || parent.data
				const index = children.findIndex(d => d.id === data.id)
				children.splice(index, 1)
			},

			loadNodes (node, resolve) {
				if (node.level === 0) {
					return resolve([{ 
										name: 'region1' 
									}, { 
										name: 'region2' 
									}])
				}
				if (node.level > 3) {
					return resolve([])
				}

				var hasChild
				if (node.data.name === 'region1') {
					hasChild = true
				} else if (node.data.name === 'region2') {
					hasChild = false
				} else {
					hasChild = Math.random() > 0.5
				}

				setTimeout(() => {
					var data
					if (hasChild) {
						data = [{
							name: 'zone' + this.count++
						}, {
							name: 'zone' + this.count++
						}]
					} else {
						data = []
					}

					resolve(data)
				}, 500)
			}			
		},
		
		watch: {
			filterText (val) {
				this.$refs.tree1.filter(val)
			}
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Tree.less' lang='less'/>
<style scoped>
</style>
