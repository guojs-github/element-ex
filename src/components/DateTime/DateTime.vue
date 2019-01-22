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

		<div class='row'>
			<el-date-picker
				v-model="date"
				type="date"
				align="right"
				placeholder="选择日期"
				:picker-options="pickerOptions">
			</el-date-picker>
			<el-date-picker
				v-model="dates"
				type="dates"
				placeholder="选择多个日期">
			</el-date-picker>
		</div>

		<div class='row'>
			<el-date-picker
				v-model="year"
				type="year"
				placeholder="选择年">
			</el-date-picker>

			<el-date-picker
				v-model="month"
				type="month"
				placeholder="选择月">
			</el-date-picker>
			
			<el-date-picker
				v-model="week"
				type="week"
				format="yyyy年 第 WW 周"
				placeholder="选择周">
			</el-date-picker>
		</div>

		<div class='row'>
			<el-date-picker
				v-model="dateRange"
				type="daterange"
				align="right"
				unlink-panels
				range-separator="至"
				start-placeholder="开始日期"
				end-placeholder="结束日期"
				:picker-options="pickerOptions2">
			</el-date-picker>
		</div>

		<div class='row'>
			<el-date-picker
				v-model="dateTime"
				type="datetime"
				:picker-options="pickerOptions3"
				placeholder="选择日期时间"
				align="right"
				default-time="11:59:59">
			</el-date-picker>
		</div>

		<div class='row'>
			<el-date-picker
				v-model="dateTimeRange"
				type="datetimerange"
				:picker-options="pickerOptions4"
				range-separator="至"
				start-placeholder="开始日期"
				end-placeholder="结束日期"
				align='right'
				:default-time='["11:59:59", "11:59:48"]'>
			</el-date-picker>
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
				endTime: '',
				date: '',
				pickerOptions: {
					disabledDate (time) { // 大于今天的日期被禁止选择
						return time.getTime() > Date.now()
					},
					shortcuts: [{
						text: '今天',
						onClick (picker) {
							picker.$emit('pick', new Date())
						}
					}, {
						text: '昨天',
						onClick (picker) {
							const date = new Date()
							date.setTime(date.getTime() - 3600 * 1000 * 24)
							picker.$emit('pick', date)
						}
					}, {
						text: '一周前',
						onClick (picker) {
							const date = new Date()
							date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
							picker.$emit('pick', date)
						}
					}]
				}, // pickerOptions
				dates: '',
				year: '',
				month: '',
				week: '',
				dateRange: '',
				pickerOptions2: {
					shortcuts: [{
						text: '最近一周',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 7)
							picker.$emit('pick', [start, end])
						}
					}, {
						text: '最近一个月',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 30)
							picker.$emit('pick', [start, end])
						}
					}, {
						text: '最近三个月',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
							picker.$emit('pick', [start, end])
						}
					}]
				}, // pickerOptions2				
				dateTime: '',
				pickerOptions3: {
					shortcuts: [{
						text: '今天',
						onClick (picker) {
							picker.$emit('pick', new Date())
						}
					}, {
						text: '昨天',
						onClick (picker) {
							const date = new Date()
							date.setTime(date.getTime() - 3600 * 1000 * 24)
							picker.$emit('pick', date)
						}
					}, {
						text: '一周前',
						onClick (picker) {
							const date = new Date()
							date.setTime(date.getTime() - 3600 * 1000 * 24 * 7)
							picker.$emit('pick', date)
						}
					}]
				}, // pickerOptions3				
				dateTimeRange: '',
				pickerOptions4: {
					shortcuts: [{
						text: '最近一周',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 7)
							picker.$emit('pick', [start, end])
						}
					}, {
						text: '最近一个月',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 30)
							picker.$emit('pick', [start, end])
						}
					}, {
						text: '最近三个月',
						onClick (picker) {
							const end = new Date()
							const start = new Date()
							start.setTime(start.getTime() - 3600 * 1000 * 24 * 90)
							picker.$emit('pick', [start, end])
						}
					}]
				} // pickerOptions4
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
