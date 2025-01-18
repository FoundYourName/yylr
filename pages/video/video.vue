<template>
	<view class="home">
		<view class="box0">
			<view class="box1">
				<a class="search" href="http://fo.jxxfjxh.cn/app/video/" target="_blank">
					<u-search placeholder="请输入搜索关键字" v-model="keyword" :showAction="false"></u-search>
				</a>
			</view>
			<view class="box2">
				<view class="box3">
					<view class="title">
						<span>{{title}}</span>
						<u-icon name="download" color="#2979ff" size="28" @click="find"></u-icon>
					</view>
					<view class="play">
						<video id="myVideo" src="/static/videos/成佛要诀 如是而已 无他秘密.mp4" @error="videoErrorCallback" autoplay="true"
							controls play-btn-position="center" show-fullscreen-btn="true" show-play-btn></video>
					</view>
				</view>

				<view class="list">
					<scroll-view class="scroll-view_H" scroll-y="true">
						<u-collapse @change="change" @close="close" @open="open">
							<u-collapse-item title="各地开示" name="Docs guide" align="center">
								<text class="u-collapse-content">
									<ul @click="find">
										<li v-for="(item,index) in addressArr" :key="index">{{item}}</li>
									</ul>
								</text>
							</u-collapse-item>
							<u-collapse-item title="讲经" name="Variety components">
								<text class="u-collapse-content">
									<ul @click="find">
										<li v-for="(item,index) in bookArr" :key="index">{{item}}</li>
									</ul>
								</text>
							</u-collapse-item>
							<u-collapse-item title="其他" name="Numerous tools">
								<text class="u-collapse-content">
									<ul @click="find">
										<li>六字大明咒修法</li>
										<li>元音老人圆寂纪实</li>
									</ul>
								</text>
							</u-collapse-item>
						</u-collapse>
					</scroll-view>
				</view>


			</view>
		</view>
		<u-icon class="icon" color="#5698c3" name="home" size="40" @click="goHome">首页</u-icon>
	</view>
</template>

<script>
	//元音老人开示摘录 https://www.bilibili.com/video/BV1PDwJetE1D
	import data from "../../static/videos.json"
	export default {
		data() {
			return {
				arr: [],
				title: "成佛要诀 如是而已 无他秘密",
				addressArr: [
					"温州打七开示", "海口开示", "上海寓所随缘开示", "美国开示", "深圳开示", "鹤壁随缘开示", "济南开示", "吉林开示", "南京开示", "陕西安康开示", "渭南路开示",
					"镇江开示", "青岛开示", "对保定学人开示", "随缘开示"
				],
				bookArr: [
					 "学佛第一要知见正","佛法修证","佛法修证心要","修行六个要点","修行要诀", "解脱歌","心经大意", "心经抉隐",  "楞严要解", "碧岩录", "大手印浅释","大手印瑜伽", "印心语录",
					"法融禅净密",  "中有成就秘笈", "心中心法十种行愿",   "美国达拉斯开示"
				]
			};
		},
		onShow() {

		},
		onLoad() {

		},
		methods: {
			open(e) {
				// console.log('open', e)
			},
			close(e) {
				// console.log('close', e)
			},
			change(e) {
				// console.log('change', e)
			},
			goHome() {
				uni.navigateTo({
					url: "/pages/index/index"
				})
			},
			find(){
				window.open("http://fo.jxxfjxh.cn/app/video")
			}
		}
	}
</script>

<style lang="scss">
	.home {


		.box0 {
			display: flex;
			flex-direction: column;
			align-items: center;
			color: black;
			height: 100vh;
			width: 100%;
			justify-content: center;
			background-color: #E8E4E1;

			.box1 {
				margin-bottom: 50px;
				a{
					text-decoration: none;
				}
			}

			.box2 {
				display: flex;
				background-color: #e9ddb6;

				.box3 {

					.title {
						display: flex;
						span {
							margin-right: auto;
							padding: 10px 20px;
							font-size: 20px;
						}
					}

					.play {
						video {
							height: 607px;
							width: 1080px;
						}
					}
				}

				.list {
					display: flex;
					flex-direction: column;
					width: 160px;//150px导致滚动条挤占ul列表宽度 讲经折叠打开底部会出现bug
					padding: 20px 10px;
					background-color: #e9ddb6;
					overflow: overlay;
					ul {
						padding-left: 0;
						li {
							padding-bottom: 10px;
						}
					}

					.scroll-view_H {
						height: 600px;
					}
				}
			}
		}
		.icon {
			position: fixed;
			right: 10px;
			bottom: 50vh;
		}
	}
</style>