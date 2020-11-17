<template>
	<view class="content">
		<view class="calendar-content" v-if="showCalendar">
			<view>
				<uni-calendar class="uni-calendar--hook"  :showMonth="false"   />
			</view>			
		</view>
		<view class="event">
			<view v-for="(item,index) in eventList" :key="index" @click="detail(index)" :class="{active:activeIndex==index}"  class="title ">
				{{item.name}}
			</view>
		</view>
	</view>
</template>

<script>
	/**
	 * 获取任意时间
	 */
	// function getDate(date, AddDayCount = 0) {
	// 	if (!date) {
	// 		date = new Date()
	// 	}
	// 	if (typeof date !== 'object') {
	// 		date = date.replace(/-/g, '/')
	// 	}
	// 	const dd = new Date(date)

	// 	dd.setDate(dd.getDate() + AddDayCount) // 获取AddDayCount天后的日期

	// 	const y = dd.getFullYear()
	// 	const m = dd.getMonth() + 1 < 10 ? '0' + (dd.getMonth() + 1) : dd.getMonth() + 1 // 获取当前月份的日期，不足10补0
	// 	const d = dd.getDate() < 10 ? '0' + dd.getDate() : dd.getDate() // 获取当前几号，不足10补0
	// 	return {
	// 		fullDate: y + '-' + m + '-' + d,
	// 		year: y,
	// 		month: m,
	// 		date: d,
	// 		day: dd.getDay()
	// 	}
	// }
	export default {
		components: {},
		data() {
			return {
				activeIndex:0,
				showCalendar: false,
				info: {
					// lunar: true,
					// range: true,
					// insert: false,
					selected: []
				},
				eventList:[
					{name:'我参加的会议'},
					{name:'我组织的会议'}
				]
			}
		},
		onReady() {
			this.$nextTick(() => {
				this.showCalendar = true
			})
			// TODO 模拟请求异步同步数据
			// setTimeout(() => {
			// 	this.info.date = getDate(new Date(), -30).fullDate
			// 	this.info.startDate = getDate(new Date(), -60).fullDate
			// 	this.info.endDate = getDate(new Date(), 30).fullDate
				// this.info.selected = [{
				// 		date: getDate(new Date(), -3).fullDate,
				// 		info: '打卡'
				// 	},
				// 	{
				// 		date: getDate(new Date(), -2).fullDate,
				// 		info: '签到',
				// 		data: {
				// 			custom: '自定义信息',
				// 			name: '自定义消息头'
				// 		}
				// 	},
				// 	{
				// 		date: getDate(new Date(), -1).fullDate,
				// 		info: '已打卡'
				// 	}
				// ]
			// }, 2000)
		},
		methods: {			
			// change(e) {				
			// 	// 模拟动态打卡
			// 	if (this.info.selected.length > 5) return
			// 	this.info.selected.push({
			// 		date: e.fulldate,
			// 		info: '打卡'
			// 	})
			// },
			detail(index){
				this.activeIndex = index
			}
			
		}
	}
</script>

<style>
	.calendar-content{
		position: relative;
	}
	.event{
		position: absolute;
		width: 100%;
		display: flex;
		margin: 30upx 10upx;
	}
	.title{
		width: 50%;
		line-height: 50upx;
		text-align: center;
		font-size: 14px;
		margin: 0upx auto;
	}
	.active{
		border-bottom: 1px solid #007AFF;
	}
</style>