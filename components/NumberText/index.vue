<template>
	<view class="number-text-container">
		<text class="number">{{number | currency}}</text>
		<text class="text">{{text}}</text>
	</view>
</template>

<script>
	export default {
		name: 'NumberText',
		props: {
			number: {
				type: Number,
				default: 0,
			},
			text: {
				type: String,
				default: '',
			},
		},
		filters: {
			currency(val) {
				if (!val || isNaN(val)) {
					return 0;
				}
				const valArr = val.toString().split('').reverse();
				const len = valArr.length;
				const result = [];
				for (let i = 0; i < len; i += 3) {
					result.unshift(valArr.slice(i, i + 3));
				}
				let str = '';
				result.forEach((arr, index) => {
					const val = arr.reverse().join('');
					str += val;
					if (index !== result.length - 1) {
						str += ',';
					}
				});
				return str;
			},
		},
	}
</script>

<style scoped lang="scss">
	.number-text-container {
		letter-spacing: 0;
		// color: #D4D4D4;
		.text {
			margin-left: 8upx;
		}
	}
</style>
