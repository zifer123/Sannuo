<template>
	<view class="index-container">
		<Tabbar
			:current="current"
			:list="list"
			@change="handleCurrentChanged"
		/>
		
		<swiper class="swiper-container" :current="current" @change="handleCurrentChanged">
			<!-- 部门页 -->
			<swiper-item>
				<ScrollYView>
					<Department />
				</ScrollYView>
			</swiper-item>
			
			<!-- 技术页 -->
			<swiper-item>
				<ScrollYView>
					<Technical />
				</ScrollYView>
			</swiper-item>
			
			<!-- 福利页 -->
			<swiper-item>
				<ScrollYView>
					<Welfare />
				</ScrollYView>
			</swiper-item>
			
			<!-- 吐槽页 -->
			<swiper-item>
				<ScrollYView>
					<Debunk />
				</ScrollYView>
			</swiper-item>
		</swiper>
		
		<AddButton @click="handleButtonClicked" />
	</view>
</template>

<script>
	import Tabbar from '../../components/Tabbar/index.vue';
	import ScrollYView from '../../components/ScrollYView/index.vue';
	import Department from './pages/department/index.vue';
	import Technical from './pages/technical/index.vue';
	import Welfare from './pages/welfare/index.vue';
	import Debunk from './pages/debunk/index.vue';
	import AddButton from '../../components/AddButton/index.vue';
	export default {
		name: 'index',
		components: {
			Tabbar,
			ScrollYView,
			Department,
			Technical,
			Welfare,
			Debunk,
			AddButton,
		},
		data() {
			return {
				current: 1,
				list: [
					{
						id: 1,
						name: '部门',
					},
					{
						id: 2,
						name: '技术',
					},
					{
						id: 3,
						name: '福利',
					},
					{
						id: 4,
						name: '吐槽',
					},
					{
						id: 5,
						name: '测试',
					},
					{
						id: 6,
						name: '测试',
					},
					{
						id: 7,
						name: '测试',
					},
					{
						id: 8,
						name: '测试',
					},
					{
						id: 9,
						name: '测试',
					},
					{
						id: 10,
						name: '测试',
					},
				],
			}
		},
		methods: {
			handleCurrentChanged(info) {
				this.current = info.detail.current;
			},
			handleButtonClicked() {
				uni.navigateTo({
					url: '../write/write',
				});
			}
		}
	}
</script>

<style scoped lang="scss">
	.index-container {
		height: 100%;
		display: flex;
		flex-direction: column;
		
		.swiper-container {
			flex: 1;
		}
	}
</style>
