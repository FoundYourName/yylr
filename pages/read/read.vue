<template>
	<view>
		<web-view :src="url"></web-view>
	</view>
</template>
 
<script>
	//直接弹出idm等下载而不能在线阅读,建议下载到本地阅读,若一定要在线阅读可以暂时关闭idm等插件捕获.
	export default {
		data() {
			return {
				url: "",//PDF路径
				viewerUrl:'/static/pdf/web/viewer.html',//用来渲染PDF的html
			};
		},
		onLoad(option) {
			console.log('=>进入了PDF预览页面')
			console.log('获取的参数=>',option.id)
			if(option.id !=undefined && option.id !='undefined' && option.id !='' && option.id !=null){
				this.url =this.viewerUrl+'?file='+encodeURIComponent(option.id); //重点在这 id就是跳到这个页面带的参数 用来定位pdf文件位置 // encodeURIComponent 函数可把字符串作为 URI 组件进行编码;

				console.log('PDF预览成功=>')
			}else{//无参就不预览PDF
				uni.showModal({//弹出提示
					title:'系统提示',//提示的标题
					content: '参数无效',//提示的内容
					confirmText:'返回',//取消按钮的文字，默认为"取消"
					showCancel:false,//是否显示取消按钮，默认为 true
					success: (res) => {
						if (res.confirm) {//监听弹窗返回按钮
							uni.navigateBack();//返回上一页
						} 
					}
				});
			}
		},
		methods: {
			
		}
	}
</script>
 
<style>
 
</style>
