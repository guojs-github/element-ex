<template>
    <div class='test-item loading'>
		<div class='title'>Loading</div>
		
		<div class='row'>
			<el-button
				type='primary'
				@click='onClickLoading'
				v-loading.fullscreen.lock='loading'>
				Loading
			</el-button>		
		</div>
	</div>
</template>

<script>
	export default {
		name: 'Loading',
		
		data () {
			return {
				loading: false
			}		
		},
		
		methods: {
			onClickLoading (e) {
				console.log('On click loading')
				
				this.loading = true
				setTimeout(() => {
					this.loading = false
				}, 3000)
			}
			
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./Loading.less' lang='less'/>
<style scoped>
</style>
