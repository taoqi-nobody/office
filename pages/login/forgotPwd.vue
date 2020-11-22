<template>
	<view class="content">
		<view class="top">
			<h2>输入手机号码</h2>
			<view class="tex">请输入您登记的手机号码</view>
		</view>
		<view class="center">
			<input type="text" value="" placeholder="您的手机号码" />
			<view class="btn-get">获取验证码</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		methods:{
			
		}
	}
</script>

<style>
	.top{
		padding: 40upx 40upx;
		
	}
	.tex{
		color: #999;
		margin-top: 15upx;
		font-size: 17px;
	}
	.center{
		padding: 0upx 40upx;
	}
	.center input{
		font-size: 25px;
		border-bottom: 1px solid #999;
		margin-bottom: 30upx;
	}
	.btn-get{
		width: 100%;
		line-height: 80upx;
		background-color: #007AFF;
		text-align: center;
		color: white;
		font-size: 15px;
		border-radius: 10upx;
	}
</style>
