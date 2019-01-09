<template>
    <div class='test-item container'>
		<div class='title'>Icons</div>
		
		<el-button type="primary" icon="el-icon-search">
			搜索
		</el-button>
		
        <div class='icons' >
			<i :id="item.id" :class="item.name" v-for="item in icons" :key="item.id"></i>
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
					{id: 2, name: 'el-icon-error'},
					{id: 3, name: 'el-icon-success'},
					{id: 4, name: 'el-icon-warning'},
					{id: 5, name: 'el-icon-question'},
					{id: 6, name: 'el-icon-back'},
					{id: 7, name: 'el-icon-arrow-left'},
					{id: 8, name: 'el-icon-arrow-down'},
					{id: 9, name: 'el-icon-arrow-right'},
					{id: 10, name: 'el-icon-arrow-up'},
					{id: 11, name: 'el-icon-caret-left'},
					{id: 12, name: 'el-icon-caret-bottom'},
					{id: 13, name: 'el-icon-caret-top'},
					{id: 14, name: 'el-icon-caret-right'},
					{id: 15, name: 'el-icon-d-arrow-left'},
					{id: 16, name: 'el-icon-d-arrow-right'},
					{id: 17, name: 'el-icon-minus'},
					{id: 18, name: 'el-icon-plus'},
					{id: 19, name: 'el-icon-remove'},
					{id: 20, name: 'el-icon-circle-plus'},
					{id: 21, name: 'el-icon-remove-outline'},
					{id: 22, name: 'el-icon-circle-plus-outline'},
					{id: 23, name: 'el-icon-close'},
					{id: 24, name: 'el-icon-check'},
					{id: 25, name: 'el-icon-circle-close'},
					{id: 26, name: 'el-icon-circle-check'},
					{id: 27, name: 'el-icon-circle-close-outline'},
					{id: 28, name: 'el-icon-circle-check-outline'},
					{id: 29, name: 'el-icon-zoom-out'},
					{id: 30, name: 'el-icon-zoom-in'},
					{id: 31, name: 'el-icon-d-caret'},
					{id: 32, name: 'el-icon-sort'},
					{id: 33, name: 'el-icon-sort-down'},
					{id: 34, name: 'el-icon-sort-up'},
					{id: 35, name: 'el-icon-tickets'},
					{id: 36, name: 'el-icon-document'},
					{id: 37, name: 'el-icon-goods'},
					{id: 38, name: 'el-icon-sold-out'},
					{id: 39, name: 'el-icon-news'},
					{id: 40, name: 'el-icon-message'},
					{id: 41, name: 'el-icon-date'},
					{id: 42, name: 'el-icon-printer'},
					{id: 43, name: 'el-icon-time'},
					{id: 44, name: 'el-icon-bell'},
					{id: 45, name: 'el-icon-mobile-phone'},
					{id: 46, name: 'el-icon-service'},
					{id: 47, name: 'el-icon-view'},
					{id: 48, name: 'el-icon-menu'},
					{id: 49, name: 'el-icon-more'},
					{id: 50, name: 'el-icon-more-outline'},
					{id: 51, name: 'el-icon-star-on'},
					{id: 52, name: 'el-icon-star-off'},
					{id: 53, name: 'el-icon-location'},
					{id: 54, name: 'el-icon-location-outline'},
					{id: 55, name: 'el-icon-phone'},
					{id: 56, name: 'el-icon-phone-outline'},
					{id: 57, name: 'el-icon-picture'},
					{id: 58, name: 'el-icon-picture-outline'},
					{id: 59, name: 'el-icon-delete'},
					{id: 60, name: 'el-icon-search'},
					{id: 61, name: 'el-icon-edit'},
					{id: 62, name: 'el-icon-edit-outline'},
					{id: 63, name: 'el-icon-rank'},
					{id: 64, name: 'el-icon-refresh'},
					{id: 65, name: 'el-icon-share'},
					{id: 66, name: 'el-icon-setting'},
					{id: 67, name: 'el-icon-upload'},
					{id: 68, name: 'el-icon-upload2'},
					{id: 69, name: 'el-icon-download'},
					{id: 70, name: 'el-icon-loading'}
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
