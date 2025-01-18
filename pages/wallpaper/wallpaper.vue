<template>
	<view class="home">
		<view class="swip">
			<u-swiper :list="list" height="100vh" circular interval="30000" autoplay="true" keyName="image"
				indicator="true" indicatorActiveColor="#fff" imgMode="aspectFit" bg-color=rgba(253,215,46,0.5)
				dicator-mode="dot"></u-swiper>
		</view>
		<u-icon class="icon" color="#5698c3" name="home" size="40" @click="goHome">首页</u-icon>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [{
					"image": "/static/wallpaper/三會彌勒尊佛會.jpg"
				}, {
					"image": "/static/wallpaper/不空绢索观音-1-2X_1060x1898_meet.fo.png"
				}, {
					"image": "/static/wallpaper/不空绢索观音（金玉观音）_2160x3610_meet.fo.png"
				}, {
					"image": "/static/wallpaper/东林大佛-阿弥陀佛（局部）-55_1284x2778_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/中国.山西.辽代木雕.水月观音像.13.美国纳尔逊阿特金森博物馆藏_压缩.png"
				}, {
					"image": "/static/wallpaper/中国.山西.辽代木雕.水月观音像.27.美国纳尔逊阿特金森博物馆藏.jpg"
				}, {
					"image": "/static/wallpaper/刺绣佛号：南无阿弥陀佛_1700x3678_meet.fo.png"
				}, {
					"image": "/static/wallpaper/北京.东城.雍和宫.戒台楼.展出文物.佛造像.千手观世音.jpg"
				}, {
					"image": "/static/wallpaper/北京.东城.雍和宫.戒台楼.展出文物.佛造像.千手观世音2.jpg"
				}, {
					"image": "/static/wallpaper/北京.东城.雍和宫.永佑殿.中间无量寿佛.57.jpg"
				}, {
					"image": "/static/wallpaper/北京.东城.雍和宫.永佑殿.左侧佛像：药师佛.39.jpg"
				}, {
					"image": "/static/wallpaper/千手观音.jpg"
				}, {
					"image": "/static/wallpaper/千手观音四十二手眼图_18.白莲花手眼.png"
				}, {
					"image": "/static/wallpaper/千手观音四十二手眼图_19.青莲花手眼.png"
				}, {
					"image": "/static/wallpaper/千手观音四十二手眼图_41.甘露手眼.png"
				}, {
					"image": "/static/wallpaper/南无阿弥陀佛 (金身)【大图编号-A992】84.7长cm_30.9宽cm_2200x5969_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/吴文莉-阿弥陀佛（西方极乐世界南无阿弥陀佛及其圣众接引图之局部）_1080x6328_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/唐代_706年_石灰岩浮雕_观音菩萨立像_01_美国宾夕法尼亚大学博物馆.jpg"
				}, {
					"image": "/static/wallpaper/四十八臂觀世音.jpg"
				}, {
					"image": "/static/wallpaper/如意輪觀世音.jpg"
				}, {
					"image": "/static/wallpaper/如意轮观音42_2160x3240_meet.fo.png"
				}, {
					"image": "/static/wallpaper/安藤德祥_南无阿弥陀佛.png"
				}, {
					"image": "/static/wallpaper/宋代_南无观世音菩萨_975x2000_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/寂照照寂.png"
				}, {
					"image": "/static/wallpaper/山西.宝宁寺.明代水陆画_024_第007幅.阿弥陀佛_山西省博物院_缩为47.jpg"
				}, {
					"image": "/static/wallpaper/山西.宝宁寺.明代水陆画_025_第008幅.阿弥陀佛_山西省博物院_缩为43.jpg"
				}, {
					"image": "/static/wallpaper/山西.宝宁寺.明代水陆画_028_第011幅.观音菩萨_山西省博物院_缩为47.jpg"
				}, {
					"image": "/static/wallpaper/广州大佛古寺—释迦摩尼佛的手指骨舍利展2.jpg"
				}, {
					"image": "/static/wallpaper/悟心铭.jpg"
				}, {
					"image": "/static/wallpaper/敦煌遗画.01.药师如来接引图.法国吉美博物馆藏.jpg"
				}, {
					"image": "/static/wallpaper/文殊問病.jpg"
				}, {
					"image": "/static/wallpaper/明代_夹紵漆金_释迦牟尼佛坐像_香港慈山寺-佛教艺术博物馆.jpg"
				}, {
					"image": "/static/wallpaper/明代_本师释迦牟尼佛_1509x2803_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/普賢菩薩.jpg"
				}, {
					"image": "/static/wallpaper/极乐世界唐卡【大图编号-A1621】3500x2298_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/極樂世界.jpg"
				}, {
					"image": "/static/wallpaper/極樂妙果圖.jpg"
				}, {
					"image": "/static/wallpaper/江苏.无锡.灵山胜境.023.灵山大佛.释迦牟尼佛.jpg"
				}, {
					"image": "/static/wallpaper/法华经普门品_观音救难图_06.救枷锁(牢狱)难_1080x1372_meet.fo.png"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）A10-008.桧木木雕千手观音.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）A10-375.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）A16-09.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）A41-052.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B41-007.png"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B42-16.png"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B43-24.毗卢观音.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B43-27.杨枝观音.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B43-33.白衣观音.jpg"
				}, {
					"image": "/static/wallpaper/浙江.舟山.普陀山.观音法界（观音圣坛）B43-36.送子观音.jpg"
				}, {
					"image": "/static/wallpaper/瓷_释迦佛_001.jpg"
				}, {
					"image": "/static/wallpaper/生死无常 弥陀作舟.png"
				}, {
					"image": "/static/wallpaper/白衣观音_1080x1543_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/真身觀世音.jpg"
				}, {
					"image": "/static/wallpaper/福建莆田普陀山-观音菩萨像.jpg"
				}, {
					"image": "/static/wallpaper/福建莆田普陀山-观音菩萨像.png"
				}, {
					"image": "/static/wallpaper/福建莆田普陀山-观音菩萨像_841x1819_meet.fo.png"
				}, {
					"image": "/static/wallpaper/華嚴三聖.jpg"
				}, {
					"image": "/static/wallpaper/藥師琉璃光佛會.jpg"
				}, {
					"image": "/static/wallpaper/西方三圣-阿弥陀佛_2000x3568_meet.fo.png"
				}, {
					"image": "/static/wallpaper/西方三聖.jpg"
				}, {
					"image": "/static/wallpaper/西方三聖1.jpg"
				}, {
					"image": "/static/wallpaper/西方接引圖.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩1.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩2.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩3.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩4.jpg"
				}, {
					"image": "/static/wallpaper/觀世音菩薩5.jpg"
				}, {
					"image": "/static/wallpaper/观世音菩萨-wi_1380x2990_meet.fo.png"
				}, {
					"image": "/static/wallpaper/观世音菩萨-白衣大士圣像【大图编号-A173】 高彩画布，沟檀头卷轴 24_60cm_1800x4479_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/观世音菩萨_5315x12047_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/观音百图：千手千眼观世音菩萨002_1997x2753_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/观音菩萨_50_1884x4020_meet.fo.png"
				}, {
					"image": "/static/wallpaper/观音菩萨_51_2036x3654_meet.fo.png"
				}, {
					"image": "/static/wallpaper/观音菩萨_52_2046x3346_meet.fo.png"
				}, {
					"image": "/static/wallpaper/观音菩萨_53_2160x3660_meet.fo.png"
				}, {
					"image": "/static/wallpaper/观音菩萨_54_2160x3396_meet.fo.png"
				}, {
					"image": "/static/wallpaper/解脱歌.png"
				}, {
					"image": "/static/wallpaper/辽代_白石贴金彩绘_释迦牟尼佛涅槃像_香港慈山寺-佛教艺术博物馆.jpg"
				}, {
					"image": "/static/wallpaper/釋迦牟尼佛會.jpg"
				}, {
					"image": "/static/wallpaper/金黄阿弥陀佛画像 【大图编号-A998】(大张，卷轴佛像) 道证法师画_1800x3863_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/阮峰-阿弥陀佛_882x1800_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛-02_2000x4336_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_1049x2400_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_1284x2778_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_1783x3504_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_JT02_2160x3874_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_JT04_2160x4106_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛_JT07_2160x3232_meet.fo.png"
				}, {
					"image": "/static/wallpaper/阿弥陀佛圣像【大图编号-A997】(相片纸输出) 118_50cm_2200x5199_meet.fo.jpg"
				}, {
					"image": "/static/wallpaper/阿彌陀佛-圓滿佛.jpg"
				}, {
					"image": "/static/wallpaper/阿彌陀佛-白玉佛.png"
				}, {
					"image": "/static/wallpaper/阿彌陀佛-紅衣佛.png"
				}, {
					"image": "/static/wallpaper/阿彌陀佛-金色佛.jpg"
				}, {
					"image": "/static/wallpaper/阿彌陀佛-金色佛1.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-不二观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-众宝观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-圆光观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-威德观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-施药观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-普悲观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-杨柳观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-水月观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-泷见观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-游戏观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-能静观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-阿么提观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-阿耨观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-鱼篮观音.png"
				}, {
					"image": "/static/wallpaper/陈明良大师敬造：三十三观音-龙头观音.png"
				}, {
					"image": "/static/wallpaper/除怨報觀世音.jpg"
				}, {
					"image": "/static/wallpaper/韋馱菩薩.jpg"
				}, {
					"image": "/static/wallpaper/莲花.jpg"
				}, {
					"image": "/static/wallpaper/莲花1.jpg"
				}, {
					"image": "/static/wallpaper/莲花2.jpg"
				}, {
					"image": "/static/wallpaper/莲花3.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-002.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-003.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-005.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-006.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-007.jpg"
				}, {
					"image": "/static/wallpaper/FG-01-010.jpg"
				}, ]
			};
		},
		methods:{
			goHome() {
				uni.navigateTo({
					url: "/pages/index/index"
				})
			}
		}
	}
</script>

<style lang="scss">
	.icon {
		position: fixed;
		right: 10px;
		bottom: 50vh;
	}
</style>