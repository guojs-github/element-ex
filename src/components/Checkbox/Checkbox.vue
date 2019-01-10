<template>
    <div class='test-item checkbox'>
		<div class='title'>Checkbox</div>
		
		<div class='row'>
			<el-checkbox v-model="checked1">备选项1</el-checkbox>
			<el-checkbox v-model="checked2" disabled>备选项</el-checkbox>
		</div>

		<div class='row'>
			<el-checkbox-group v-model="checkList1" :min='1' :max='3'>
				<el-checkbox label="复选框 A"></el-checkbox>
				<el-checkbox label="复选框 B"></el-checkbox>
				<el-checkbox label="复选框 C"></el-checkbox>
				<el-checkbox label="禁用" disabled></el-checkbox>
				<el-checkbox label="选中且禁用" disabled></el-checkbox>
			</el-checkbox-group>
		</div>

		<div class='row'>
			<el-checkbox :indeterminate="isIndeterminate" v-model="checkAll" @change="onCheckAllChange">全选</el-checkbox>
			<div style="margin: 15px 0;">
				<el-checkbox-group v-model="checkedCities" @change="onCheckedCitiesChange">
					<el-checkbox v-for="city in cities" :label="city" :key="city">{{city}}</el-checkbox>
				</el-checkbox-group>
			</div>		
		</div>
		
		<div class='row'>
			<el-checkbox-group v-model="checkedCities" size="small">
				<el-checkbox-button v-for="city in cities" :label="city" :disabled="city === '北京'" :key="city">{{city}}</el-checkbox-button>
			</el-checkbox-group>
		</div>

		<div class='row'>
			<el-checkbox v-model="checked3" label="备选项1" border></el-checkbox>
			<el-checkbox v-model="checked4" label="备选项2" size='small' border></el-checkbox>
			<el-checkbox v-model="checked5" label="备选项3" size='mini' border></el-checkbox>
		</div>		
	</div>
</template>

<script>
	const cityOptions = ['上海', '北京', '广州', '深圳']
	export default {
		name: 'Checkbox',
		
		data () {
			return {
				checked1: true,
				checked2: false,
				checked3: true,
				checked4: true,
				checked5: true,
				checkList1: ['选中且禁用'],
				checkAll: false,
				isIndeterminate: true,
				checkedCities: ['上海', '北京'],
				cities: cityOptions
			}		
		},
		
		methods: {
			onCheckAllChange (value) {
				console.log('value:' + value)
				
				this.checkedCities = value ? cityOptions : []
				this.isIndeterminate = false
			},
			
			onCheckedCitiesChange (checkedList) {
				console.log('checkedList:' + JSON.stringify(checkedList))

				let checkedCount = checkedList.length
				this.checkAll = checkedCount === this.cities.length
				this.isIndeterminate = checkedCount > 0 && checkedCount < this.cities.length
			}
			
			/*****************************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Checkbox.less' lang='less'/>
<style scoped>
</style>
