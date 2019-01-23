<template>
    <div class='test-item upload'>
		<div class='title'>Upload</div>
		
		<div class='row'>
			<el-upload
				class="upload-demo"
				action="https://jsonplaceholder.typicode.com/posts/"
				:file-list="fileList"
				:on-preview="onPreview"
				:on-remove="onRemove"
				:on-success='onSuccess'
				list-type="picture">
				<el-button size="small" type="primary">点击上传</el-button>
				<div slot="tip" class="el-upload__tip">只能上传jpg/png文件，且不超过500kb</div>
			</el-upload>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Upload',
		
		data () {
			return {
				fileList: [{
					name: 'food.jpeg', 
					url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'
				}, {
					name: 'food2.jpeg', 
					url: 'https://fuss10.elemecdn.com/3/63/4e7f3a15429bfda99bce42a18cdd1jpeg.jpeg?imageMogr2/thumbnail/360x360/format/webp/quality/100'
				}]			
			}		
		},
		
		methods: {
			onRemove (file, fileList) {
				console.log(file, fileList)
			},
			
			onPreview (file) {
				console.log(file)
			},
			
			onSuccess (response, file, fileList) {
				console.log('On upload file success')
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Upload.less' lang='less'/>
<style scoped>
</style>
