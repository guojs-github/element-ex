<template>
    <div class='test-item tag'>
		<div class='title'>Tag</div>
		
		<div class='row'>
			<el-tag
				:key='tag.name'
				v-for='tag in tags'
				closable
				:type = 'tag.type'
				:size = 'tag.size'
				:disable-transitions='false'
				@close='onClose(tag)'>
				{{tag.name}}
			</el-tag>

			<el-input
				v-if='inputVisible'
				class='input-new-tag'
				v-model='inputValue'
				ref='saveTagInput'
				size='small'
				@keyup.enter.native='onInputConfirm'
				@blur='onInputConfirm'>
			</el-input>

			<el-button 
				v-else 
				class='button-new-tag' 
				size='small' 
				@click='onShowInput'>
				增加标签
			</el-button>
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Tag',
		
		data () {
			return {
				tags: [{
					name: '标签一',
					type: '',
					size: ''
				}, {
					name: '标签二',
					type: 'success',
					size: 'medium'
				}, {
					name: '标签三',
					type: 'info',
					size: 'small'
				}, {
					name: '标签四',
					type: 'warning',
					size: 'mini'
				}, {
					name: '标签五',
					type: 'danger',
					size: 'mini'
				}],
				inputVisible: false,
				inputValue: ''
			}		
		},
		
		methods: {
			onClose (tag) {
				this.tags.splice(this.tags.indexOf(tag), 1)
			},

			onShowInput () {
				this.inputVisible = true
				this.$nextTick(_ => {
					this.$refs.saveTagInput.$refs.input.focus()
				})
			},

			onInputConfirm () {
				let inputValue = this.inputValue
				if (inputValue) {
					this.tags.push({
						name: inputValue,
						type: 'danger',
						size: 'mini'
					})
				}
				this.inputVisible = false
				this.inputValue = ''
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Tag.less' lang='less'/>
<style scoped>
</style>
