<template>
	<view class="body">
		<!-- 提示语 -->
		<view class="tipe clearfix">
			<view class="fl">
				<image src="../../static/index2.png" mode=""></image>
			</view>
			<view class="txt fl">输入日期和参会人数可快速筛选符合的会议室哟！</view>
		</view>
		
		<!-- 会议选择条件 -->
		<view>
			<view class="time clearfix">
				<view class="icon_time fl">
					<image src="../../static/index2.png" mode=""></image>
				</view>
				<picker mode="date" :value="date" @change="bindDateChange">
				    <view class="fl">会议日期: <text>{{date}}</text></view>
				</picker>
				<!-- <view class="fl">会议日期： <text>2020-11-11</text></view> -->
				<picker class="icon" mode="date" :value="date" @change="bindDateChange"> > </picker>
			</view>
			<view class="time clearfix">
				<view class="icon_time fl">
					<image src="../../static/index2.png" mode=""></image>
				</view>
				<view class="fl">参会人数：  <input type="text" value="1" /></view>
			</view>
		</view>
		
		<!-- 会议室选择 -->
		<view class="choice">
			<view class="choice_box">
				<view class="choice_content">
					<view class="choice_title">第一会议室</view>
					<view>可容纳206人</view>
				</view>
				<view class="choice_condition" @click="toggle('bottom')">预定请况 ></view>
			</view>
			
			<view class="choice_box">
				<view class="choice_content">
					<view class="choice_title">第一会议室</view>
					<view>可容纳206人</view>
				</view>
				<view class="choice_condition" @click="toggle('bottom')">预定请况 ></view>
			</view>
			
			<view class="choice_box">
				<view class="choice_content">
					<view class="choice_title">第一会议室</view>
					<view>可容纳206人</view>
				</view>
				<view class="choice_condition" @click="toggle('bottom')">预定请况 ></view>
			</view>
			
			<view class="choice_box">
				<view class="choice_content">
					<view class="choice_title">第一会议室</view>
					<view>可容纳206人</view>
				</view>
				<view class="choice_condition" @click="toggle('bottom')">预定请况 ></view>
			</view>
		</view>
		
		
		<!-- 会议室选择 -->
		<uni-popup id="popup" ref="popup" :type="type" :animation="false">
			<view class="popup-content">
				<view class="popup-box clearfix">
					<view class="title fl">第一会议室</view>
					<view class="number fr">可容纳206人</view>
				</view>
				<view>
					<radio-group @change="radioChange">
						<label class="uni-list-cell uni-list-cell-pd" v-for="(item, index) in items" :key="item.value">
							<view class="popup-box clearfix">
								<view class="fl">
									<radio :checked="index === current" />
								</view>
								<view class="fl">{{item.name}}</view>
							</view>
						</label>
					</radio-group>
				</view>
			</view>
		</uni-popup>
		
	</view>
	
	
	
</template>

<script>
	export default {
		data() {
			const currentDate = this.getDate({
			    format: true
			})
			return {
				date: currentDate,
				type: 'bottom',
				items: [{
						name: '10:00-12:00',
					},
					{
						name: '10:00-12:00',
					},
					{
						name: '10:00-12:00',
					},
					{
						name: '10:00-12:00',
					},
					{
						name: '10:00-12:00',
					},
					{
						name: '10:00-12:00',
					},
					{
							name: '10:00-12:00',
						},
						{
							name: '10:00-12:00',
						},
						{
							name: '10:00-12:00',
						},
						{
							name: '10:00-12:00',
						},
						{
							name: '10:00-12:00',
						},
						{
							name: '10:00-12:00',
						},
				],
				current: 99
			}
		},
		methods: {
			// 预约时间
			bindDateChange: function(e) {
				console.log(e)
			    this.date = e.detail.value
			},
			// 获取时间
			getDate(type) {
			    const date = new Date();
			    let year = date.getFullYear();
			    let month = date.getMonth() + 1;
			    let day = date.getDate();
				
			    month = month > 9 ? month : '0' + month;
			    day = day > 9 ? day : '0' + day;
			    return `${year}-${month}-${day}`;
			},
			
			/**
			 * 打开基础内容
			 */
			toggle(type) {
				this.type = type
				this.$refs.popup.open()
			},
			
			
			
			// confirmShare() {
			// 	this.$refs.popupShare.open()
			// },
		}
	}
</script>

<style>
	@charset "UTF-8";
	/* 清除浮动 */
	.clearfix:after{
	  display:block; 
	  content:"clear"; 
	  height:0; 
	  clear:both; 
	  padding-top:5rpx;
	  overflow:hidden; 
	  visibility:hidden;
	}
	.fl{
	float: left
	}
	.fr{
	float: right
	}
	image{
	  width: 100%;
	  height: 100%;
	}
	.body{
		width: 100%;
		height: 100vh;
		background-color: #EEEEEE;
		overflow: hidden;
	}
	
	.tipe{
		background-color: #999966;
		padding: 0 20upx;
	}
	.tipe image{
		width: 32upx;
		height: 32upx;
		display: block;
		margin: 8upx 12rpx;
	}
	.txt{
		font-size: 28upx;
		color: #F0AD4E;
		line-height: 48upx;
	}
	
	.time{
		padding: 0 40upx;
		background-color: #FFFFFF;
	}
	.icon_time{
		width: 42upx;
		height: 40upx;
		display: block;
		margin: auto;
		margin-top: 8upx;
		margin-right: 14upx;
	}
	.icon{
		font-size: 32rpx;
		line-height: 88upx;
		float: right;
	}
	.time view{
		font-size: 32rpx;
		line-height: 88upx;
	}
	.time text{
		margin-left: 10upx;
		color: #007AFF;
	}
	.time input{
		margin-left: 10upx;
		color: #007AFF;
		float: right;
		/* line-height: 88upx; */
		margin-top: 22upx;
	}
	
	.choice{
		margin-top: 40upx;
		background-color: #FFFFFF;
	}
	.choice_box{
		padding: 0 40upx;
		border-bottom: 1px solid #EEEEEE;
		display: flex;
	}
	.choice_content{
		width: 50%;
		font-size: 28upx;
		color: #EEEEEE;
		line-height: 1.5;
		margin-top: 38upx;
	}
	.choice_content .choice_title{
		font-size: 34upx;
		color: #000000;
	}
	.choice_condition{
		width: 50%;
		font-size: 28upx;
		line-height: 140upx;
		text-align: right;
		color: #007AFF;
	}
	
	.popup-content {
		height: 500upx;
		background-color: #fff;
		overflow: auto;
	}
	.popup-box{
		padding: 0 30upx;
		border-bottom: 1px solid #EEEEEE;
	}
	.popup-box .title{
		font-size: 36upx;
		font-weight: 500;
		line-height: 108upx;
	}
	.popup-box .number{
		font-size: 32upx;
		color: #EEEEEE;
		line-height: 108upx;
	}
	.uni-list-cell {
		justify-content: flex-start
	}
	.popup-box view{
		font-size: 32upx;
		line-height: 88upx;
	}
	
</style>
