<template>
	<view class="fBox">
		<view class="who">
			<li @click="setArr1"><text>大愚法师</text></li>
			<li @click="setArr2"><text>王骧陆居士</text></li>
			<li @click="setArr3"><text>元音老人</text></li>
			<li @click="setArr4"><text>禅宗辑要</text></li>
		</view>

		<view class="books">		
			<view class="book" v-for="(item,index) in booksArr0" :key="index">

				<view class="read" @click="toRead(item.url)">
					<view class="img">
						<p class="title">{{item.title}}</p>
						<p class="subtitle">{{item.subtitle}}</p>
					</view>
					<view class="info">
						<p class="title">{{item.title}}</p>
					</view>
				</view>
			</view>
			<u-icon class="icon" color="#5698c3" name="home" size="40" @click="goHome">首页</u-icon>

		</view>

	</view>
</template>

<script>

	export default {
		data() {
			return {


				booksArr: [{
						"url": "/static/books/元音老人/心密三祖元音老人略传-佛法修证心要丛书.pdf",
						"title": "元音老人略传",
						"subtitle": "元音老人"
					},
					{
						"url": "/static/books/元音老人/佛法修证心要全集.pdf",
						"title": "佛法修证心要",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/学佛第一要知见正-佛法修证心要丛书.pdf",
						"title": "第一要知见正",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/学佛无难，但观自在-佛法修证心要丛书.pdf",
						"title": "学佛无难但观自在",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/问答集-佛法修证心要丛书.pdf",
						"title": "修证心要问答集",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/《悟心铭》浅释-佛法修证心要丛书.pdf",
						"title": "悟心铭",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/略论明心见性-佛法修证心要丛书.pdf",
						"title": "略论明心见性",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/心经抉隐-佛法修证心要丛书.pdf",
						"title": "心经抉隐",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/耳根圆通法门-佛法修证心要丛书.pdf",
						"title": "耳根圆通法门",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/桥流水不流-佛法修证心要丛书.pdf",
						"title": "桥流水不流",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/大手印浅释-佛法修证心要丛书.pdf",
						"title": "大手印浅释",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/《解脱歌》浅释-佛法修证心要丛书.pdf",
						"title": "解脱歌",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/《碧岩录》讲座-佛法修证心要丛书.pdf",
						"title": "碧岩录",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/消业往生与带业往生-佛法修证心要丛书.pdf",
						"title": "消业与带业往生",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/净土指归-佛法修证心要丛书.pdf",
						"title": "净土指归",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/楞严要解-佛法修证心要丛书.pdf",
						"title": "楞严要解",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/禅海微澜-佛法修证心要丛书.pdf",
						"title": "禅海微澜",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/如何消除贪嗔痴慢疑-佛法修证心要丛书.pdf",
						"title": "消除贪嗔痴慢疑",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/法身、报身、化身-佛法修证心要丛书.pdf",
						"title": "法身、报身、化身",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/谈谈往生西方的关键问题-佛法修证心要丛书.pdf",
						"title": "往生西方关键问题",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/心中心密法打七开示-佛法修证心要丛书.pdf",
						"title": "打七开示",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/融禅净密于一体的心中心法-佛法修证心要丛书.pdf",
						"title": "融禅净密于一体",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/传心中心法灌顶时之开示-佛法修证心要丛书.pdf",
						"title": "灌顶时开示",
						"subtitle": "元音老人"
					}, {
						"url": "/static/books/元音老人/中有释要-佛法修证心要丛书.pdf",
						"title": "中有释要",
						"subtitle": "元音老人"
					}
				],
				booksArr0: [],
				booksArr1: [{
						"url": "/static/books/大愚法师/大愚阿阇黎略传.pdf",
						"title": "大愚阿阇黎略传",
						"subtitle": "大愚法师"
					}, {
						"url": "/static/books/大愚法师/修行要诀 大愚阿阇黎.pdf",
						"title": "修行要诀",
						"subtitle": "大愚法师"
					},
					{
						"url": "/static/books/大愚法师/解脱歌 大愚阿阇黎.pdf",
						"title": "解脱歌",
						"subtitle": "大愚法师"
					}
				],
				booksArr2: [{
						"url": "/static/books/王骧陆上师/《王骧陆居士全集 上》.pdf",
						"title": "王骧陆居士全集上",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/《王骧陆居士全集 下》.pdf",
						"title": "王骧陆居士全集下",
						"subtitle": "王骧陆上师"
					}, {
						"url": "/static/books/王骧陆上师/王骧陆居士 序传-王骧陆居士全集.pdf",
						"title": "王骧陆居士序传",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/入佛明宗答问-王骧陆居士全集.pdf",
						"title": "入佛明宗答问",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/乙亥讲演录-王骧陆居士全集.pdf",
						"title": "乙亥讲演录",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/学佛最初之决定-王骧陆居士全集.pdf",
						"title": "学佛最初之决定",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/印心语录-王骧陆居士全集.pdf",
						"title": "印心语录",
						"subtitle": "王骧陆上师"
					}, {
						"url": "/static/books/王骧陆上师/文辞与书信-王骧陆居士全集.pdf",
						"title": "文辞与书信",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/圆觉经抉隐-王骧陆居士全集.pdf",
						"title": "圆觉经抉隐",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/仁王护国般若波罗蜜多经略说-王骧陆居士全集.pdf",
						"title": "仁王护国经略说",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/佛说阿弥陀经分段正义-王骧陆居士全集.pdf",
						"title": "阿弥陀经分段正义",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/佛说阿弥陀经经义略说-王骧陆居士全集.pdf",
						"title": "阿弥陀经经义略说",
						"subtitle": "王骧陆上师"
					},

					{
						"url": "/static/books/王骧陆上师/养生论-王骧陆居士全集.pdf",
						"title": "养生论",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/净土修持问题-王骧陆居士全集.pdf",
						"title": "净土修持问题",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/净土印心法要-王骧陆居士全集.pdf",
						"title": "净土印心法要",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/千偈瑜珈焰口-王骧陆居士全集.pdf",
						"title": "千偈瑜珈焰口",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/大鉴禅师法宝坛经述旨-王骧陆居士全集.pdf",
						"title": "坛经述旨",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/学佛丛谈-王骧陆居士全集.pdf",
						"title": "学佛丛谈",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/心经随说-王骧陆居士全集.pdf",
						"title": "心经随说",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/心锽-王骧陆居士全集.pdf",
						"title": "心锽",
						"subtitle": "王骧陆上师"
					},

					{
						"url": "/static/books/王骧陆上师/点滴-王骧陆居士全集.pdf",
						"title": "点滴",
						"subtitle": "王骧陆上师"
					},

					{
						"url": "/static/books/王骧陆上师/般若波罗蜜多心经分段贯释-王骧陆居士全集.pdf",
						"title": "心经分段贯释",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/般若波罗蜜多心经白话分段解释-王骧陆居士全集.pdf",
						"title": "心经白话分段解释",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/观微杂说-王骧陆居士全集.pdf",
						"title": "观微杂说",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/金刚经义随说-王骧陆居士全集.pdf",
						"title": "金刚经义随说",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/金刚经释义意见-王骧陆居士全集.pdf",
						"title": "金刚经释义意见",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/金刚般若波罗蜜经分段贯释-王骧陆居士全集.pdf",
						"title": "金刚经分段贯释",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/金刚般若波罗蜜经受持法略说-王骧陆居士全集.pdf",
						"title": "金刚经受持法略说",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/金刚般若波罗蜜经白话述义-王骧陆居士全集.pdf",
						"title": "金刚经白话述义",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/阿弥陀心要-王骧陆居士全集.pdf",
						"title": "阿弥陀心要",
						"subtitle": "王骧陆上师"
					},
					{
						"url": "/static/books/王骧陆上师/整理后记-王骧陆居士全集.pdf",
						"title": "整理后记",
						"subtitle": "王骧陆上师"
					}
				],
				booksArr3: [{
					"url": "/static/books/禅宗辑要/七佛传法偈.pdf",
					"title": "七佛传法偈",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/临济语录.pdf",
					"title": "临济语录",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/入道四行观.pdf",
					"title": "入道四行观",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/大颠禅师注解心经.pdf",
					"title": "大颠禅师注解心经",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/岩头全奯禅师语录.pdf",
					"title": "岩头全奯禅师语录",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/无门关.pdf",
					"title": "无门关",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/本师化迹.pdf",
					"title": "本师化迹",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/证道歌.pdf",
					"title": "证道歌",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/赵州谂禅师语录.pdf",
					"title": "赵州谂禅师语录",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/达摩大师悟性论.pdf",
					"title": "达摩大师悟性论",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/达摩大师破相论.pdf",
					"title": "达摩大师破相论",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/达摩大师血脉论.pdf",
					"title": "达摩大师血脉论",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/黄檗断际禅师宛陵录.pdf",
					"title": "黄檗断际禅师宛陵录",
					"subtitle": "禅宗辑要"
				}, {
					"url": "/static/books/禅宗辑要/黄檗禅师传心法要.pdf",
					"title": "黄檗禅师传心法要",
					"subtitle": "禅宗辑要"
				}]

			};

		},
		onShow() {

		},
		onLoad() {
			this.booksArr0 = this.booksArr

		},
		methods: {
			toRead(id) {
				uni.navigateTo({
					url: "/pages/read/read?id="+id
				})
			},
			goHome() {
				uni.navigateTo({
					url: "/pages/index/index"
				})
			},
			setArr1() {
				this.booksArr0 = this.booksArr1
				console.log("大愚法师");
			},
			setArr2() {
				this.booksArr0 = this.booksArr2
				console.log("王骧陆上师");
			},
			setArr3() {
				this.booksArr0 = this.booksArr
				console.log("元音老人");
			},
			setArr4() {
				this.booksArr0 = this.booksArr3
				console.log("禅宗辑要");
			}

		}
	}
</script>

<style lang="scss">
	.fBox {
		display: flex;
		flex-direction: column;

		.who {
			background-color: #DAA520;
			height: 50px;
			display: flex;
			justify-content: space-around;
			align-items: center;
			text-align: center;

			text {
				color: #000;
				font-weight: bold;
				font-size: 20px;
			}
		}

		.books {
			display: flex;
			justify-content: space-evenly; 
			flex-wrap: wrap;


			.book {

				.read {
					width: 100%;
					height: 100%;
					.img {
						width: 160px;
						height: 160px;
						background-size: cover;
						background-image: url(../../static/imgs/book_item_bg.png);
						transition: all ease .4s;
						margin: 20px 40px;
						display: flex;

						p {
							position: relative;
							text-align: center;
							font-size: 13px;
							writing-mode: vertical-lr;
						}

						.title {
							left: 40px;
							color: #DAA520;
						}

						.subtitle {
							padding-top: 20px;
							left: 110px;
							text-align: left;
							color: #fff;
						}
					}

					.info {
						.title {
							color: #1A1A1A;
							text-align: center;
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
	}
</style>