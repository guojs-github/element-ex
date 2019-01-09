<template>
	<div class='test'>
		<Layout/>
		<Container/>
		<Icons/>
	</div>
</template>

<script>
	import Layout from './Layout/Layout'
	import Container from './Container/Container'
	import Icons from './Icons/Icons'
	export default {
		name: 'Test',

		data () {
			return {
			}
		},

		components: {
			Layout,
			Container,
			Icons
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
