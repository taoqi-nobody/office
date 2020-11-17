<template>
	<view class="logininfo">
		<view class="top">
			<image src="../../static/bg.jpg" mode=""></image>
			<view class="top-content">
				<view class="top-content-title">					
					<view class="name">未登录</view>
					<view class="">欢迎你使用会议室登陆系统！！</view>	
				</view>	
				<view class="top-content-center">
					<view class="top-content-center-title">
						<view @click="changecolor(index)" class="name " :class="{active:titles==index}" v-for="(item,index) in title" :key="index">{{item.name}}</view>
						
					</view>
					<view class="top-content-center-input">						
						<view class="user" v-if="user">
							<view class="username" >
								<uni-icons class="icons" type="person"></uni-icons>
								<input type="text" value="" placeholder="账户" />
							</view>
							<view class="pwd">
								<uni-icons class="icons" type="locked"></uni-icons>
								<input type="password" value="" placeholder="密码" />
							</view>
						</view>					
						<view class="phone" v-if="phone">
							<view class="phone-tel">
								<uni-icons class="icons" type="phone"></uni-icons>
								<input type="text" value="" placeholder="手机号" />
							</view>
							<view class="line2">
								<view class="yanzm">
									<uni-icons class="icons" type="email"></uni-icons>
									<input type="password" value="" placeholder="验证码" />
								</view>
								<view class="getyzm">获取验证码</view>
							</view>
						</view>
					</view>
					<view class="btn">
						<view class="btn-login">登陆</view>
						<view class="forgotPwd" @click="changePwd">找回密码></view>
					</view>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				titles:0,
				user:true,
				phone:false,
				title:[					
					{name:'账号密码登陆'},
					{name:'手机号登陆'}				
				]
			}
		},
		methods: {
			changecolor(index){
				this.titles=index
				if(index==0){
					this.user=true
					this.phone=false
				}else if(index==1){
					this.user=false
					this.phone=true
				}			
			},
			changePwd(){
				uni.navigateTo({
					url:'./forgotPwd'
				})
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
	.top-content{
		width: 100%;
		position: absolute;
		top: 0;
		padding: 20px 20px;
	}
	.top-content-title{
		color: white;
		line-height: 1.5;
	}
	.top-content-title .name{
		font-size: 25px;
	}
	.top-content-center{
		margin-top: 40upx;
		width: 100%;
		background-color: white;
		box-shadow:0 0 9px 3px rgba(49,32,0,0.1);
		/* line-height: 400upx; */
		border-radius: 20upx;
		
	}
	.top-content-center-title{
		display: flex;
		/* align-items: center; */
		justify-content: space-around;
		border-bottom: 1px solid #eee;
		margin: 30upx 20upx;
		/* line-height: 100upx; */
	}
	.active{
		border-bottom: 1px solid #007AFF;
		color: #007AFF;
	}
	.top-content-center .name{
		width: 50%;
		text-align: center;
		line-height: 80upx;
		/* color: #000000; */
		font-size: 18px;
	}
	.username{
		font-size: 15px;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border: 1px solid #999;
		margin: 20upx 20upx;
		line-height: 80upx;
		border-radius: 10upx;
		padding-left: 15upx;
		
	}
	.username .icons{
		/* width: 20%; */
		/* line-height: ; */
	}
	.username input{
		/* width: 80%; */
		
	}
	.pwd{
		display: flex;
		align-items: center;
		justify-content: flex-start;
		margin: 30upx 20upx;
		line-height: 80upx;
		border: 1px solid #999;
		border-radius: 10upx;
		padding-left: 15upx;
	}
	.line2{
		display: flex;
		align-items: center;
		justify-content: flex-start;
		/* border: 1px solid #999; */
		margin: 20upx 20upx;
		line-height: 80upx;
		border-radius: 10upx;
		/* padding-left: 15upx; */
	}
	.phone-tel{
		font-size: 15px;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border: 1px solid #999;
		margin: 20upx 20upx;
		line-height: 80upx;
		border-radius: 10upx;
		padding-left: 15upx;
	}
	.yanzm{
		width: 70%;
		font-size: 15px;
		display: flex;
		align-items: center;
		justify-content: flex-start;
		border: 1px solid #999;
		/* margin: 20upx 20upx; */
		line-height: 80upx;
		border-radius: 10upx;
		padding-left: 15upx;
	}
	.btn-login{
		/* width: 100%; */
		color: white;
		background-color: #007AFF;
		line-height: 80upx;
		margin: 50upx 20upx;
		text-align: center;
	}
	.getyzm{
		width: 30%;
		font-size: 15px;
		/* display: flex;
		align-items: center; */
		/* justify-content: flex-start; */
		/* border: 1px solid #999; */
		/* margin: 20upx 20upx; */
		line-height: 80upx;
		border-radius: 10upx;
		/* padding-left: 15upx; */
		background-color: #eee;
		border:1px solid #007AFF;
		color: #007AFF;
		text-align: center; 
	}
	.forgotPwd{
		text-align: center;
		line-height: 30upx;
		color: #007AFF;
		padding-bottom: 100upx;
	}	
</style>
