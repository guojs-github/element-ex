<template>
    <div class='test-item transfer'>
		<div class='title'>Transfer</div>
		
		<div class='row'>
			<el-transfer
				style="text-align: left; display: inline-block"
				v-model="value"
				:props='{
					key: "index",
					label: "description"
				}'			
				filterable
				:filter-method="onFilter"
				:left-default-checked="[2, 3]"
				:right-default-checked="[1]"
				:titles='["来源", "目标"]'
				:button-texts="['回左边来', '到右边去']"
				:format='{
					noChecked: "${total}",
					hasChecked: "${checked}/${total}"
				}'
				@change='onChange'
				:data='data'>
				<span slot-scope='{ option }'>{{ option.index }} - {{ option.description }}</span>
				<el-button class='transfer-footer' slot="left-footer" size="small">左侧操作</el-button>
				<el-button class='transfer-footer' slot="right-footer" size="small">右侧操作</el-button>
			</el-transfer>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Transfer',
		
		data () {
			const generateData = () => {
				const data = []
				for (let i = 1; i <= 15; i++) {
					data.push({
						index: i, // 通过:props映射为key
						description: `备选项 ${i}`, // 通过:props映射为label
						disabled: i % 4 === 0
					})
				}

				return data
			}
			
			return {
				data: generateData(),
				value: [1],
				onFilter: function (query, item) { // label有命中或者label的拼音有命中都可以
					return item.description.indexOf(query) > -1
				}
			}		
		},
		
		methods: {			
			onChange (value, direction, movedKeys) {
				console.log(value, direction, movedKeys)
				// value 为移动后，选中的项目
				// direction 本次移动方向
				// moveKeys 本次被移动的项目
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Transfer.less' lang='less'/>
<style scoped>
</style>
