<template>
	<view class="add-container">
		<view class="add" @tap.stop="handleButtonClicked">
			+
		</view>
	</view>
</template>

<script>
	export default {
		name: 'AddButton',
		data() {
			return {
				
			}
		},
		methods: {
			handleButtonClicked() {
				this.$emit('click');
			}
		}
	}
</script>

<style scoped lang="scss">
	.add-container {
		position: fixed;
		/* #ifdef MP */
		bottom: 15px;
		/* #endif */
		/* #ifdef H5 */
		bottom: 65px;
		/* #endif */
		right: 15px;
		
		perspective: 192upx;
		.add {
			position: relative;
			width: 96upx;
			height: 96upx;
			background-color: rgba(0,131,249, .8);
			border-radius: 50%;
			font-size: 28px;
			text-align: center;
			line-height: 96upx;
			color: #FFF;
			transition: transform .3s ease-out;
			&.hidden {
				transform: rotateY(90deg);
			}
			
			&::after {
				content: "";
				display: block;
				position: absolute;
				width: 100%;
				height: 100%;
				top: 0;
				left: 0;
				pointer-events: none;
				background-image: radial-gradient(circle, #000 10%, rgba(0, 0, 0, 0) 10.01%);
				background-repeat: no-repeat;
				background-position: 50%;
				transform: scale(10);
				opacity: 0;
				transition: transform .5s, opacity 1s;
			}
			
			&:active::after {
				transform: scale(0);
				opacity: .2;
				transition: 0s;
			}
		}
	}
</style>
