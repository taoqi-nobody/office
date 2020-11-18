<template>
	<view>
		<view class="top">					
			<picker  @change="bindPickerChange" :value="index"  :range="array" >
				<view class="ttitle">
					<image class="t1" src="../../static/more.png" mode=""></image>
					<span style="font-size: 15px;margin: 0 25upx;">会议室</span>
					<image class="t2" src="../../static/bt.png" mode=""></image>
				</view>			
			</picker>
			<view class="btn" v-if="reset">重置</view>
		</view>
		<record  class="recods"></record>
		
		 <!-- <picker @change="bindPickerChange" :value="index" :range="array">
			<view class="uni-input">{{array[index]}}</view> 
		</picker> -->
	</view>
</template>

<script>
	import record from '../../components/news.vue'
	export default {
		
		components:{
			record
		},
		data() {
			return {
				array: ['第一会议室', '第二会议室', '第三会议室', '第四会议室'],
				index: 0,
				reset:false
			}
		},
		methods:{
			bindPickerChange: function(e) {				
				this.index = e.target.value
				if(this.index!=''){
					this.reset = true
				}
			},
		}
	}
</script>

<style>
	.top{
		
		width: 100%;
		display: flex;
		
		
		
	
	}
	.ttitle{
		border: 1px solid #eee;
		background-color: #FAFAFA;
		padding: 10upx 10upx;
		margin: 20upx 20upx;
		line-height: 70upx;
		
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.top .t1{
		width: 50upx;
		height: 50upx;
	}
	.top .t2{
		width: 35upx;
		height: 35upx;
	}
	.recods{
		margin-top: 50upx;
	}
	.btn{
		width: 150upx;
		line-height: 60upx;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #FFEDED;
		color: red;
		margin: 20upx 20upx;
		border-radius: 10upx;
		font-size: 16px;
	}
</style>
