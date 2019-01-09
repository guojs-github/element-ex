<template>
    <div class='test-item container'>
		<div class='title'>Icons</div>
		
		<el-button type="primary" icon="el-icon-search">
			搜索
		</el-button>
		
        <div :id="item.id" class='' v-for="item in icons" :key="item.id">
			<i :class="item.name"></i>
		</div>
    </div>
</template>

<script>
export default {
	name: 'Icons',
	
	data () {
		return {
			icons: [
				{id: 1, name: 'el-icon-info'},
				{id: 1, name: 'el-icon-error'}
			]
		}		
	},
	
	methods: {
	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Icons.less' lang='less'/>
<style scoped>
</style>
