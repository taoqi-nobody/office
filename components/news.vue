<template>
	<view class="body">
		<!-- 消息通知内容 -->
		<view class="news_box clearfix">
			<view class="clearfix">
				<view class="title fl">参加会议</view>
				<view class="time fr">2020-11-11 11:11</view>
			</view>
			<view class="content">
				【参加会议】系统管理原通知你与2020年09月28日 15:00分在XXX1会议室参加信息中心日常会议
			</view>
			<view class="state fr">我已阅读</view>
		</view>
		
		<!-- <view class="news_box clearfix">
			<view class="clearfix">
				<view class="title fl">参加会议</view>
				<view class="time fr">2020-11-11 11:11</view>
			</view>
			<view class="content">
				【参加会议】系统管理原通知你与2020年09月28日 15:00分在XXX1会议室参加信息中心日常会议
			</view>
			<view class="state fr">我已阅读</view>
		</view> -->
		
		<!-- <view class="news_box clearfix">
			<view class="clearfix">
				<view class="title fl">参加会议</view>
				<view class="time fr">2020-11-11 11:11</view>
			</view>
			<view class="content">
				【参加会议】系统管理原通知你与2020年09月28日 15:00分在XXX1会议室参加信息中心日常会议
			</view>
			<view class="state fr">我已阅读</view>
		</view> -->
		
		
	</view>
	
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>
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
	
	.news_box{
		width: 684upx;
		margin: 15upx auto 0;
		padding: 18upx;
		background-color: #FFFFFF;
	}
	.title{
		font-size: 32upx;
		line-height: 56upx;
	}
	.time{
		font-size: 16rpx;
		line-height: 56upx;
		color: #C0C0C0;
	}
	.content{
		width: 682upx;
		font-size: 16upx;
		border-bottom: 1upx solid #EEEEEE;
		padding:10upx 0 30upx;
	}
	
	.state{
		font-size: 16rpx;
		line-height: 56upx;
		color: #C0C0C0;
	}
	

</style>
