<template>
    <div class='test-item pagination'>
		<div class='title'>Pagination</div>
		
		<div class='row'>
			<el-pagination
				@size-change='onSizeChange'
				@current-change='onCurrentChange'
				:current-page='currentPage'
				:page-sizes='[100, 200, 300, 400]'
				:page-size='100'
				layout='total, sizes, prev, pager, next, jumper'
				:total='400'
				small
				background>
			</el-pagination>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Pagination',
		
		data () {
			return {
				currentPage: 1
			}		
		},
		
		methods: {
			onSizeChange (val) {
				console.log(`每页 ${val} 条`)
			},
			
			onCurrentChange (val) {
				console.log(`当前页: ${val}`)
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Pagination.less' lang='less'/>
<style scoped>
</style>
