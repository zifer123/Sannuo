<template>
	<scroll-view class="tabbar-container" scroll-x scroll-with-animation :scroll-left="scrollLeft">
		<!-- <view class="tabbar-list"> -->
			<block v-for="(item, index) in list" :key="item.id">
				<view 
					class="tabbar-item" 
					:class="{active: current === index}" 
					@tap="handleItemClicked(index)"
				>
					{{item.name}}
				</view>
			</block>
		<!-- </view> -->
	</scroll-view>
</template>

<script>
	export default {
		name: 'tabbar',
		props: {
			current: {
				type: Number,
				default: 0,
			},
			list: {
				type: Array,
				default: [],
			},
		},
		data() {
			return {
				
			}
		},
		methods: {
			handleItemClicked(index) {
				// this.current = index;
				this.$emit('change', {
					detail: {
						current: index,
					},
				});
			}
		},
		computed: {
			scrollLeft() {
				return (this.current - 2) * uni.upx2px(148);
			},
		},
	}
</script>

<style scoped lang="scss">
	.tabbar-container {
		letter-spacing: 1upx;
		font-size: 14px;
		border-bottom: 1px solid #E5E5E5;
		box-shadow: 0 1px 1px 3px rgba(0, 0, 0, .25);
		white-space: nowrap;
		.tabbar-item {
			position: relative;
			display: inline-block;
			width: 148upx;
			height: 88upx;
			text-align: center;
			line-height: 88upx;
			color: #BBBBBB;
			transition: color .3s ease-out;
			&::after {
				position: absolute;
				content: '';
				width: 0;
				left: 50%;
				bottom: 0;
				transform: translateX(-50%);
				height: 6upx;
				background-color: #333333;
				border-radius: 8upx;
				transition: width .3s ease-out;
			}
			&.active {
				color: #333;
				&::after {
					width: 50%;
				}
			}
		}
	}
</style>
