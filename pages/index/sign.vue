<template>
	<view>
		<u-select v-model="show" mode="single-column" :list="list" @confirm="confirm"></u-select>
		<u-button @click="show = true">打开</u-button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				show: false,
				list: [
					{
						value: '1',
						label: '江'
					},
					{
						value: '2',
						label: '湖'
					}
				],
			}
		}
	}
</script>

<style>
	.titleline{
		width: 100%;
		height: 500upx;
		overflow: auto;
		
	}
</style>
