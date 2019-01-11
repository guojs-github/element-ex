<template>
    <div class='test-item cascader'>
		<div class='title'>Cascader级联选择器</div>
		
		<div class='row'>
			<el-cascader
				:options="options"
				v-model="selectedOptions"
				expand-trigger='hover'
				change-on-select
				filterable
				@change="onChange">
			</el-cascader>

			<el-cascader
				:options="options2"
				v-model="selectedOptions2"
				expand-trigger='hover'
				@active-item-change="onItemChange"
				:props="props">
			</el-cascader>			
		</div>
		
	</div>
</template>

<script>
	export default {
		name: 'Cascader',
		
		data () {
			return {
				selectedOptions: ['ziyuan', 'sketch'],
				selectedOptions2: [],
				options: [{
					value: 'zhinan',
					label: '指南',
					children: [{
						value: 'shejiyuanze',
						label: '设计原则',
						children: [{
								value: 'yizhi',
								label: '一致'
							}, {
								value: 'fankui',
								label: '反馈'
							}, {
								value: 'xiaolv',
								label: '效率'
							}, {
								value: 'kekong',
								label: '可控'
							}]
						}, {
						value: 'daohang',
						label: '导航',
						disabled: true,
						children: [{
							value: 'cexiangdaohang',
							label: '侧向导航'
						}, {
							value: 'dingbudaohang',
							label: '顶部导航'
						}]
					}]
				}, {
				  value: 'ziyuan',
				  label: '资源',
				  children: [{
					value: 'axure',
					label: 'Axure Components'
				  }, {
					value: 'sketch',
					label: 'Sketch Templates'
				  }, {
					value: 'jiaohu',
					label: '组件交互文档'
				  }]
				}],
				options2: [{
					label: '江苏',
					cities: []
				}, {
					label: '浙江',
					cities: []
				}],
				props: {
					value: 'label',
					children: 'cities'
				}
			}		
		},
		
		methods: {
			onChange (value) {
				console.log('value:' + value)
			},
			
			onItemChange (value) {
				console.log('active item:', value)
				
				setTimeout(_ => {
					if (value.indexOf('江苏') > -1 && !this.options2[0].cities.length) {
						this.options2[0].cities = [{
							label: '南京'
						}]
					} else if (value.indexOf('浙江') > -1 && !this.options2[1].cities.length) {
						this.options2[1].cities = [{
							label: '杭州'
						}]
					}
				}, 300)			
			}
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Cascader.less' lang='less'/>
<style scoped>
</style>
