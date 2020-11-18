<template>
	<view class="content">
		<view class="top">					
			<picker  mode="date" :value="date"  @change="bindPickerChange"    >
				<view class="ttitle">
					<image class="t1" src="../../static/more.png" mode=""></image>
					<span style="font-size: 15px;margin: 0 10upx;">会议日期</span>
					<image class="t2" src="../../static/bt.png" mode=""></image>
				</view>			
			</picker>
			<picker  @change="bindPickerChange" :value="index"  :range="array" >
				<view class="ttitle">
					<image class="t1" src="../../static/more.png" mode=""></image>
					<span style="font-size: 15px;margin: 0 10upx;">会议类型</span>
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
			const currentDate = this.getDate({
			            format: true
			        })
			return {
				array: ['外部议室', '内部议室'],
				index: 0,
				reset:false,
				date: currentDate,
			}
		},
		methods:{
			bindPickerChange: function(e) {				
				this.index = e.target.value
				if(this.index!=''){
					this.reset = true
				}
			},
			 getDate(type) {
			            const date = new Date();
			            let year = date.getFullYear();
			            let month = date.getMonth() + 1;
			            let day = date.getDate();
			
			            if (type === 'start') {
			                year = year - 60;
			            } else if (type === 'end') {
			                year = year + 2;
			            }
			            month = month > 9 ? month : '0' + month;;
			            day = day > 9 ? day : '0' + day;
			            return `${year}-${month}-${day}`;
			        }
		}
	}
</script>

<style>
	.content{
		background-color: #eee;
	}
	.top{
		height: 130upx;
		width: 100%;
		display: flex;
		align-items: center;
		background-color: white;
		
		
	
	}
	.ttitle{
		border: 1px solid #eee;
		background-color: #FAFAFA;
		padding: 10upx 10upx;
		margin: 0upx 10upx;
		
		height: 70upx;
		
		display: flex;
		justify-content: space-between;
		align-items: center;
	}
	.top .t1{
		width: 40upx;
		height: 40upx;
	}
	.top .t2{
		width: 30upx;
		height: 30upx;
	}
	.recods{
		margin-top: 20upx;
	}
	.btn{
		width: 150upx;
		line-height: 70upx;
		display: flex;
		justify-content: center;
		align-items: center;
		background-color: #FFEDED;
		color: red;
		margin: 20upx 16upx;
		border-radius: 10upx;
		font-size: 16px;
	}
</style>
