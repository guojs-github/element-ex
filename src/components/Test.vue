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
		<Cascader/>
		<SwitchDemo/>
		<Slider/>
		<DateTime/>
		<Upload/>
		<Rate/>
		<ColorPicker/>
		<Transfer/>
		<Form/>
		<Table/>
		<Tag/>
		<Progress/>
		<Tree/>
		<Pagination/>
		<Badge/>
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
	import Cascader from './Cascader/Cascader'
	import SwitchDemo from './SwitchDemo/SwitchDemo'
	import Slider from './Slider/Slider'
	import DateTime from './DateTime/DateTime'
	import Upload from './Upload/Upload'
	import Rate from './Rate/Rate'
	import ColorPicker from './ColorPicker/ColorPicker'
	import Transfer from './Transfer/Transfer'
	import Form from './Form/Form'
	import Table from './Table/Table'
	import Tag from './Tag/Tag'
	import Progress from './Progress/Progress'
	import Tree from './Tree/Tree'
	import Pagination from './Pagination/Pagination'
	import Badge from './Badge/Badge'
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
			Select,
			Cascader,
			SwitchDemo,
			Slider,
			DateTime,
			Upload,
			Rate,
			ColorPicker,
			Transfer,
			Form,
			Table,
			Tag,
			Progress,
			Tree,
			Pagination,
			Badge
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
