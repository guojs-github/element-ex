<template>
    <div class='test-item select'>
		<div class='title'>Select</div>
		
		<div class='row'>
			<el-select 
				v-model="value" 
				placeholder="请选择" 
				clearable multiple filterable allow-create default-first-option>
				<el-option-group 
					v-for='group in options' 
					:key='group.label' 
					:label='group.label'>
					<el-option 
						v-for="item in group.options" 
						:key="item.value"
						:label="item.label"
						:value="item.value"
						:disabled='item.disabled'>
						<span style='float: left' class='select-test-item-label'>{{ item.label }}</span>
						<span style='float: left' class='select-test-item-value'>{{ '-' + item.value }}</span>
					</el-option>
				</el-option-group>
			</el-select>
		</div>

	</div>
</template>

<script>
	export default {
		name: 'Select',
		
		data () {
			return {
				value: '',
				options: [{
					label: '热门',
					options: [{
						value: '选项1',
						label: '黄金糕'
					}, {
						value: '选项2',
						label: '双皮奶'
					}]
				}, {
					label: '菜品',
					options: [{
						value: '选项3',
						label: '蚵仔煎',
						disabled: true
					}, {
						value: '选项4',
						label: '龙须面'
					}, {
						value: '选项5',
						label: '北京烤鸭'						
					}]
				}]
			}		
		},
		
		methods: {
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Select.less' lang='less'/>
<style scoped>
</style>
