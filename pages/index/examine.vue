<template>
	<view class="content">
		<view class="event">
			<view v-for="(item,index) in eventList" :key="index" @click="detail(index)" :class="{active:activeIndex==index}"  class="title ">
				{{item.name}}
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				activeIndex:0,
				eventList:[
					{name:'待审核'},
					{name:'已审核'}
				]
			}
		},
		methods:{
			detail(index){
				this.activeIndex = index
			}
		}
	}
</script>

<style>
	.event{
		
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
