<template>
	<view class="technical-container">
		<view class="article-list">
		
			<block v-for="(item, index) in list" :key="index">
				<view class="article-list-item">
					<view class="title">如何逼自己做到真改变？</view>
					
					<view class="article-main">
						<view class="article-main-left">
							<view class="user-info">
								<image class="user-avatar" src="/static/img/avatars/1.jpg" mode="aspectFill"></image>
								<text class="user-name">ben大叔</text>
							</view>
							
							<view class="article-main-content">
								覆你的人生观这篇文章会颠覆你的人生观这篇文章会颠覆你的人生观一
							</view>
						</view>
						
						<view class="article-main-right">
							<image class="img" src="/static/img/avatars/1.jpg" mode="aspectFill"></image>
						</view>
					</view>
					
					<view class="footer">
						<view class="footer-left">
							一天前
						</view>
						
						<view class="footer-right">
							<NumberText
								:number="20244"
								text="赞同"
							/>
							<text class="separation">·</text>
							<NumberText
								:number="450"
								text="评论"
							/>
						</view>
					</view>
				</view>
			</block>
			
		</view>
	</view>
</template>

<script>
	import NumberText from '../../../../components/NumberText/index.vue';
	export default {
		name: 'technical',
		components: {
			NumberText,
		},
		data() {
			return {
				list: [
					1,3,5,7,9,11,13,15,17,19
				]
			}
		}
	}
</script>

<style scoped lang="scss">
	.technical-container {
		
		.article-list {
			
			.article-list-item {
				display: flex;
				flex-direction: column;
				background-color: #fff;
				padding: 28upx;
				margin: 18upx 0;
				.title {
					padding: 8upx 0;
					font-size: 15px;
					color: #303030;
					font-weight: bold;
				}
				
				.article-main {
					display: flex;
					padding: 14upx 0;
					.article-main-left {
						flex: 1;
						padding-right: 8upx;
						.user-info {
							display: flex;
							align-items: center;
							.user-avatar {
								width: 48upx;
								height: 48upx;
								border-radius: 50%;
							}
							.user-name {
								margin-left: 8upx;
								color: #6C6C6C;
							}
						}
						
						.article-main-content {
							color: #636363;
							padding: 8upx 0;
							
							position: relative;
							max-height: 3em;
							line-height: 1.5;
							overflow: hidden;
							
							&::before {
								content: '...';
								position: absolute;
								z-index: 1;
								bottom: 0;
								right: 0;
								// width: 1.5em;
								padding-left: 3px;
								// box-sizing: border-box;
								background-color: white;
							}
							&::after {
								content: '';
								display: inline-block;
								position: absolute;
								z-index: 2;
								width: 100%;
								height: 100%;
								background-color: white;
							}
						}
					}
					.article-main-right {
						margin-left: auto;
						width: 192upx;
						height: 128upx;
						background-color: #ccc;
						border-radius: 8upx;
						.img {
							width: 100%;
							height: 100%;
						}
					}
				}
				
				.footer {
					display: flex;
					justify-content: space-between;
					color: #959595;
					.footer-left {
						
					}
					
					.footer-right {
						display: flex;
						.separation {
							padding: 0 6upx;
						}
					}
				}
			}
		}
	}
</style>
