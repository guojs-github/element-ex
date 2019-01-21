<template>
    <div class='test-item date-time'>
		<div class='title'>Date & Time</div>
		
		<div class='row'>
			<el-time-select
				v-model='value'
				:picker-options='{
					start: "08:30",
					step: "00:15",
					end: "18:30"
				}'
				placeholder='选择时间'>
			</el-time-select>
		</div>

		<div class='row'>
			<el-time-picker
				v-model='value2'
				:picker-options='{
					selectableRange: "18:30:00 - 20:30:00"
				}'
				placeholder='任意时间点'>
			</el-time-picker>
		</div>
		
		<div class='row'>
			<el-time-select
				placeholder='起始时间'
				v-model='startTime'
				:picker-options='{
					start: "08:30",
					step: "00:15",
					end: "18:30",
					maxTime: endTime
				}'>
			</el-time-select>
			<el-time-select
				placeholder='结束时间'
				v-model='endTime'
				:picker-options='{
					start: "08:30",
					step: "00:15",
					end: "18:30",
					minTime: startTime
				}'>
			</el-time-select>
		</div>
		
		<div class='row'>
			<el-time-picker
				is-range
				v-model="value3"
				range-separator="至"
				start-placeholder="开始时间"
				end-placeholder="结束时间"
				placeholder="选择时间范围">
			</el-time-picker>
		</div>

	</div>
</template>

<script>
	export default {
		name: 'DateTime',
		
		data () {
			return {
				value: '10:15',
				value2: new Date(2019, 1, 21, 19, 59, 58),
				value3: [new Date(2019, 1, 21, 10, 59, 58), new Date(2019, 2, 21, 11, 1, 58)],
				startTime: '',
				endTime: ''
			}		
		},
		
		methods: {
			/**********************/
		}
	}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped src='../Test.less' lang='less'/>
<style scoped src='./DateTime.less' lang='less'/>
<style scoped>
</style>
