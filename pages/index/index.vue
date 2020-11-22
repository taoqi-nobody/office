<template>
	<view class="content">
		<view class="top">
			<image  src="../../static/bg.jpg" mode=""></image>
			<view class="substance">
				<view class="top-login">
					<view class="top-login-left">
						<view class="title">未登录</view>
						<view class="">欢迎你使用会议室登陆系统！！</view>
					</view>
					<view class="top-login-right" @click="login">立刻登陆</view>
				</view>
				<view class="top-meeting">
					<view class="top-meeting-news">
						<view class="top-meeting-news-title" @click="meet"> 我的会议</view>
						<!-- <view class="dots">
							<view class="dot"></view>
							<view class="dot"></view>
						</view> -->
						<view class="line"></view>
					</view>
					<view class="">|</view>
					<view class="top-meeting-news">
						<view class="top-meeting-news-title" @click="mynews"> 我的消息</view>
						<!-- <view class="dots">
							<span class="dot"></span>
							<span class="dot"></span>
						</view> -->
						<view class="line"></view>
					</view>
				</view>
			</view>
		</view>
		<view class="scorll-list">
			<scroll-view scroll-x="true" class="scroll-box" >
				<view class="list-box">
					<block v-for="(item,index) in list" :key="index">
						<view class="ss1" @click="detail(index)">
							<image :src="item.img" style="width: 60upx; height: 60upx;" mode=""></image>
							<view class="">{{item.title}}</view>
						</view>
					</block>
				</view>
			</scroll-view>
		</view>
		<view class="date">
			<view class="name">
				<view class="title">会议日程</view>
				<view class="right">
					<view class="" @click="meet">更多</view>
					<image src="../../static/right.png" style="width: 15upx; height: 15upx;" mode=""></image>
				</view>
			</view>
			<view class="time">
				<scroll-view class="time-list" scroll-x="true" >
					<view class="time-list-box">
						<block v-for="(item,index) in timer">
							<view class="week " @click="changeWk(index)" :class="{changeWeek:weekIndex==index}" >
								<view class="">{{item.day}}</view>
								<view class="">{{item.date}}</view>
							</view>
						</block>
					</view>
				</scroll-view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				weekIndex:'',
				list:[
					{img:'../../static/index1.png',title:'预定'},
					{img:'../../static/index2.png',title:'签到'},
					{img:'../../static/index3.png',title:'出席'},
					{img:'../../static/index4.png',title:'查询'},
					{img:'../../static/query.png',title:'进程'},
					{img:'../../static/index1.png',title:'审核'}
				],
				timer:[
					{day:'今天',date:'11-01'},
					{day:'星期四',date:'11-02'},
					{day:'星期五',date:'11-03'},
					{day:'星期六',date:'11-04'},
					{day:'星期天',date:'11-05'},
					{day:'星期一',date:'11-06'},
					{day:'星期二',date:'11-07'},
				]
			}
		},
		onLoad() {

		},
		methods: {
			login(){
				uni.navigateTo({
					url:'../login/login'
				})
			},
			detail(index){
				if(index==0){
					uni.navigateTo({
						url:'./book'
					})
				}else if(index==1){
					uni.navigateTo({
						url:'./sign'
					})
				}else if(index==2){
					uni.navigateTo({
						url:'./attend'
					})
				}else if(index==3){
					uni.navigateTo({
						url:'./poll'
					})
				}else if(index==4){
					uni.navigateTo({
						url:'./process'
					})
				}else if(index==5){
					uni.navigateTo({
						url:'./examine'
					})
				}
			},
			mynews(){
				uni.navigateTo({
					url:'./information'
				})
			},
			meet(){
				uni.navigateTo({
					url:'./mymeet'
				})
			},
			changeWk(index){
				this.weekIndex = index
			}
		}
	}
</script>

<style>
	.top{
		position: relative;
	}
	.top image{
		width: 100%;
		height: 400upx;
	}
	.substance{
		width: 100%;
		position: absolute;
		top: 0;
		padding: 20px 20px;
	}
	.top-login{
		/* width: 100%; */
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.top-login-left{
		color: white;
		width: 85%;
		line-height: 1.5;
	}
	.top-login-left .title{
		font-size: 25px;
	}
	.top-login-right{
		/* float: right; */
		width: 170upx;
		line-height: 60upx;
		border-radius: 35upx;
		text-align: center;
		background-color: white;
		color: #2B85E4;
	}
	.top-meeting{
		height: 150upx;
		margin-top: 50upx;
		background-color: white;
		border-radius: 20upx;
		display: flex;
		justify-content: flex-start;
		padding: 10upx 20upx;
		align-items: center;
		/* align-items: center; */
	}
	.top-meeting-news{
		
		width: 30%;
		line-height: 40upx;
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		align-items: center;
	}
	.top-meeting-news-title{
		font-size: 16px;
	}
	.line{
		width: 40%;
		height: 5upx;
		background-color: #007AFF;
		margin-top: 15upx;
	}
	/* .dots{
		display: flex;
		justify-content: space-between;
		width: 30upx;
	}
	.top-meeting-news .dot{
		width: 10upx;
		height: 10upx;
		background-color: #000000;
	} */
	.scorll-list{
		/* box-sizing: border-box; */
		margin-top: 20upx;
		width: 100%;
		display: flex;
	}
	.scroll-box{
		flex: 1;
		overflow: hidden;
		/* box-sizing: border-box; */
		padding: 0 20upx;
		
	}
	.list-box{
		/* width: 100%; */
		line-height: 40upx;
		display: flex;
		flex-wrap: nowrap;
		/* justify-content: center; */
		
	}
	.ss1{
		width: 18%;
		flex-shrink: 0;
		margin-left: 20upx;
	}
	.date{
		margin-top: 20upx;
		padding: 10upx 20upx;
		border-bottom: 2px solid #eee;
	}
	.name{
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 10upx 20upx;
	}
	.name .title{
		font-size: 20px;
	}
	.right{
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 14%;
		color: #666666;
	}
	.time{
		margin-top: 20upx;
		width: 100%;
	}
	.time-list{
		overflow: hidden;
		box-sizing: border-box;
	}
	.time-list-box{
		width: 100%;
		display: flex;
		flex-wrap: nowrap;
		box-sizing: border-box;
		height: 150upx;
	}
	.week{
		flex-shrink: 0;
		width: 20%;
		height: 120upx;
		margin-left: 10upx;
		background-color: #eee;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.changeWeek{
		background-color: #DCEEFD;
		color: #007AFF;
		border: 1px solid #007AFF;
		width: 22%;
		height: 125upx;
		border-radius: 10upx;
	}
</style>
