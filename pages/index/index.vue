<template>
	<view class="home">
		<view class="tabs">
			<u-tabs @click="toPage" :list="list" :current="num" lineheight="12" lineWidth="55" lineColor=#ffffff
				:activeStyle="{
				    color: '#ffffff',
				    fontWeight: 'bold',
				    transform: 'scale(1.05)'
				}" :inactiveStyle="{
				    color: '#ffffff',
				    transform: 'scale(1)'
				}" itemStyle="padding-left: 30px; padding-right: 30px; height: 40px;padding-top:150rpx;padding-bottom:8px">
			</u-tabs>

		</view>
		<view class="lbt">
			<u-swiper :list="list1" :height="h" showTitle circular interval="30000" autoplay="true" keyName="image"
				indicator="true" indicatorActiveColor="#fff" imgMode="aspectFit" bg-color=rgba(0,0,0,0.1)
				dicator-mode="dot"></u-swiper>
		</view>
		<view class="footer">
			<text>免责声明 &nbsp;&nbsp; | &nbsp;&nbsp;联系我们 <br /></text>
			<text>Copyright©2024 by Chaos &nbsp;&nbsp;&nbsp;&nbsp;***网安备 ********号&nbsp;&nbsp;&nbsp;&nbsp;友情链接：
				<a href="http://www.xmzj.org/">心密之家</a>
				<a href="http://fo.jxxfjxh.cn/">佛法修证心要</a>
			</text>
		</view>
	</view>
</template>

<script>
	const lineBg =
		"data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACgAAAAOCAYAAABdC15GAAAACXBIWXMAABYlAAAWJQFJUiTwAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAFxSURBVHgBzZNRTsJAEIb/WTW+lpiY+FZPIDew3ABP4GJ8hxsI9zBpOYHeQDwBPQI+mRiRvpLojtPdYhCorQqF/6GdbGd2vvwzBXZcNAt4oj1ANeUoAT5iqkUjbEFLHNmhD1YPEvpZ3ghkGlVDCkc94/BmHMq998I5ONiY1ZBfpKAyuOtgAc5yOEDmYEWNh32BHF91sGHZHmwW4azciN9aQwnz3SJEgOmte+R2tdLprTYoa50mvuomlLpD4Y3oQZnov6D2RzCqI93bWOHaEmAGqQUyRBlZR1WfarcD/EJ2z8DtzDGvsMCwpm8XOCfDUsVOCYhiqRxI/CTQo4UOvjzO7Pow18vfywneuUHHUUxLn55lLw5JFpZ8bEUcY8oXdOLWiHLTxvoGpLqoUmy6dBT15o/ox3znpoycAmxUsiJTbs1cmxeVKp+0zmFIS7bGWiVghC7Vwse8jFKAX9eljh4ggKLLv7uaQvG9/F59Oo2SouxPu7OTCxN/s8wAAAAASUVORK5CYII=";

	export default {
		components: {

		},
		data() {
			return {

				list: [{
					name: '首页'
				}, {
					name: '藏经阁',

				}, {
					name: '讲经堂',
				}, {
					name: '壁纸栏'
				}, {
					name: '下载区'
				}],
				list1: [{
						image: '/static/videos/一念断处 了了分明.mp4',
						poster: "/static/imgs/悟心铭.jpg",
						// title: '一念断处 了了觉知',
						type: "video"
					}, {
						image: '/static/imgs/悟心铭.jpg',
						title: '不着见闻 荡然无住',
					}, {
						image: '/static/imgs/寂照照寂.png',
						title: '寂寂断见闻 荡荡心无著'
					}, {
						image: '/static/imgs/jtg.png',
						title: '凡所有相 皆是虚妄 不取于相 如如不动'
					},
					{
						image: '/static/imgs/永嘉证道歌.png',
						title: '应无所住 而生其心'
					}, {
						image: '/static/imgs/心经.webp',
						title: '知幻即离 离幻即觉'
					}, {
						image: '/static/imgs/01.png',
						title: '外不被境牵 内不随念转'
					}, {
						image: '/static/imgs/03.png',
						title: '不是息心除妄想 只缘无事可思量'
					}, {
						image: '/static/imgs/04.png',
						title: '一翳在眼 空华乱坠 知是空华 即无轮转'
					}, {
						image: '/static/imgs/00.png',
						title: '不惧念起 唯恐觉迟'
					}, {
						image: '/static/imgs/02.jpg',
						title: '青山本不动 白云任来去'
					}, {
						image: '/static/imgs/01.jpg',
						title: '了则业障本来空 不了应须还宿债'
					}, {
						image: '/static/imgs/16.jpg',
						title: '梦里明明有六趣 觉后空空无大千'
					}, {
						image: '/static/imgs/11.jpg',
						title: '万古是非浑若梦 一句弥陀作大舟'
					}
				],
				// list1: [{
				// 	image: '/static/imgs/1.jpg',
				// 	title: '应无所住 而生其心',
				// }, {
				// 	image: '/static/imgs/2.jpg',
				// 	title: '菩提本无树 明镜亦非台'
				// }, {
				// 	image: '/static/imgs/3.jpg',
				// 	title: '本来无一物 何处惹尘埃'
				// }],
				title: "火中生金莲",
				h: "700px",
				num: 0
			}
		},
		onShow() {
			this.read()
		},
		onLoad() {

		},
		methods: {
			read() {
				var _that = this
				plus.io.resolveLocalFileSystemURL('/static/imgs/1.jpg', function(entry) {
					console.log(entry);
					return
					entry.file(function(file) {
						var fileReader = new plus.io.FileReader();
						fileReader.readAsText(file, 'utf-8');
						fileReader.onloadend = function(evt) {
							console.log(evt.target.result);
							_that.list = JSON.parse(evt.target.result)
							fileReader.abort()
						}
					});
				}, function(e) {
					console.log("Resolve file URL failed: " + e.message);
				});
			},

			toPage(index) {
				console.log(index.index);
				if (index.index == 0) {
					uni.navigateTo({
						url: "/pages/index/index"
					})
				} else if (index.index == 1) {
					uni.navigateTo({
						url: "/pages/books/books"
					})
				} else if (index.index == 2) {
					uni.navigateTo({
						url: "/pages/video/video"
					})
				} else if (index.index == 3) {
					uni.navigateTo({
						url: "/pages/wallpaper/wallpaper"
					})
				} else if (index.index == 4) {
					window.open("http://www.xmzj.org/article")
				}
				this.num = index.index
			}
		}

	}
</script>

<style lang="scss">
	.home {
		height: 100vh;
		width: 100%;
		background-image: url("../../static/imgs/莲花.jpg");
		background-size: 100%;

		.tabs {
			display: flex;
			justify-content: center;

			span {
				font-size: 100px;
			}
		}

		.lbt {
			padding: 20px 0;
		}

		.footer {
			flex: 1;
			width: 990px;
			height: auto;
			margin: 0 auto;
			overflow: hidden;
			text-align: center;
			font-size: 15px;
			font-weight: bold;
			color: #ffffff;

			a {
				padding-right: 20px;
				color: #ffffff;
				text-decoration: none;
			}
		}
	}
</style>