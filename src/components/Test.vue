<template>
	<div class='test'>
		<Layout/>
		<Container/>
		<Icons/>
		<Button/>
		<Radio/>
		<Checkbox/>
		<Input/>
		<InputNumber/>
		<Select/>
	</div>
</template>

<script>
	import Layout from './Layout/Layout'
	import Container from './Container/Container'
	import Icons from './Icons/Icons'
	import Button from './Button/Button'
	import Radio from './Radio/Radio'
	import Checkbox from './Checkbox/Checkbox'
	import Input from './Input/Input'
	import InputNumber from './InputNumber/InputNumber'
	import Select from './Select/Select'
	export default {
		name: 'Test',

		data () {
			return {
			}
		},

		components: {
			Layout,
			Container,
			Icons,
			Button,
			Radio,
			Checkbox,
			Input,
			InputNumber,
			Select
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
