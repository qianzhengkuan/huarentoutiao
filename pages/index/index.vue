<template>
	<view >
		<!-- 自定义导航 -->
		<uni-nav-bar :border="false" :fixed="true" :statusBar="true" backgroundColor="#149da3">
			<!-- 左边 -->
			<view slot="left" class="d-flex a-center j-center text-white ">
				<text class="iconfont icon-dingwei font-big"></text>
				<text>中国大陆</text>
			</view>
			<!-- 中间 -->
			<view class=" d-flex flex-1 bg-light rounded  a-center text-light-muted" style="height:80rpx;">
				<text class="iconfont icon-icon- mx-2 font-big"></text>
				<text class="text-dark font-md">搜你想搜的</text>
			</view>
			<!-- 右边 -->
			<view slot="right" class="d-flex flex-column a-center j-center text-white" style="line-height: 0.8">
				<text class="iconfont icon-zhaoxiangji font-big"></text>
				<text>发布</text>
			</view>
		</uni-nav-bar>
		<!-- 内容部分 -->
		<view class="" style="">
			<!-- 顶部选项卡 -->
			<view class="d-flex border-bottom " style="position: fixed;z-index: 999;background-color: #FFFFFF;height: 100rpx;width: 100%;">
				<view class="d-flex a-center j-center" style="width: 85%;">
					<scroll-view scroll-x :scroll-into-view="scrollInto" scroll-with-animation  style="width: 100%;white-space: nowrap;">
						<view
							class="scroll-row-item font-lg "
							v-for="(item, index) in tabBar"
							:key="index"
							:id="'tab' + index"
							:class="tabIndex === index ? 'text-main' : ''"
							@click="changeTab(index)"
							style="padding: 0 20rpx ;padding-left: 20rpx;"
						>
							{{ item.name }}
						</view>
					</scroll-view> 
				</view>
				<view class="d-flex j-center a-center" style=" width:15% ;position: absolute;right: 0;top: 0;height: 100%;" >
					<text class="iconfont icon-gengduo font-lg"></text>
				</view>
			</view>
			

			<!-- 可以滑动 列表-->
			<view class="" style="padding-top: 100rpx;" >
				<swiper :duration="500" :current="tabIndex" @change="onChangeTab" :style="'height:' + scrollH + 'rpx;'" >
					<swiper-item v-for="item in 20" :key="item">
						<scroll-view scroll-y="true" :style="'height:' + scrollH + 'rpx;'">
							<!-- 列表样式 -->
							<view class="p-2 mb-2">
								<view class="font-lg text-light-muted">中国新规:"洋留守学生"无法报考大学</view>
								<view class="line-h-md">
									<text class="mr-2 border px-1 rounded text-main" style="border-color: #149da3;">置顶</text>
									<text class="mr-2 text-h">华人头条</text>
									<text class="text-h">5分钟前</text>
								</view>
							</view>
							<!-- 轮播图 -->
							<swiper :indicator-dots="true" circular :autoplay="true" :interval="3000" :duration="1000" style="margin: 0 15rpx;" indicator-active-color="#FFFFFF">
								<swiper-item style="border-radius: 15rpx;">
									<view class="swiper-item">
										<image class="border-radius-5" src="../../static/image/datapic/16.jpg" mode="" style="height: 350rpx;width: 100%;border-radius: 15rpx;"></image>
									</view>
								</swiper-item>
								<swiper-item style="border-radius: 15rpx;">
									<view class="swiper-item">
										<image class="border-radius-5" src="../../static/image/banner3.jpg" mode="" style="height: 350rpx;width: 100%;border-radius: 15rpx;"></image>
									</view>
								</swiper-item>
								<swiper-item style="border-radius: 15rpx;">
									<view class="swiper-item">
										<image class="border-radius-5" src="../../static/image/datapic/16.jpg" mode="" style="height: 350rpx;width: 100%;border-radius: 15rpx;"></image>
									</view>
								</swiper-item>
								<swiper-item style="border-radius: 15rpx;">
									<view class="swiper-item">
										<image class="border-radius-5" src="../../static/image/banner3.jpg" mode="" style="height: 350rpx;width: 100%;border-radius: 15rpx;"></image>
									</view>
								</swiper-item>
							</swiper>
							
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
							<view class="d-flex mt-2 p-2 border-bottom">
								<view class="flex-1">
									<view class="font-lg text-light-muted line-h-md text-ellipsis2 mb-2">电视剧《婚姻的两种猜想》开机 鼓励女性活出自己的爱情</view>
									<view class="line-h-md">
										<text class="mr-2 text-h">中新网</text>
										<text class="text-h">13分钟前</text>
										<text class="mr-2 border rounded line-h0 p-1 mt-1 " style="float: right;"><text class="iconfont icon-guanbi font-sm text-light-muted"></text></text>
									</view>
								</view>
								<view class="" style="width:250rpx ;">
									<image src="../../static/image/banner2.jpg" style="width:250rpx;height: 180rpx;border-radius: 15rpx;" mode=""></image>
								</view>
							</view>
						</scroll-view>
					</swiper-item>
				</swiper>
			</view>
		</view>
	</view>
</template>

<script>
import uniNavBar from '@/components/uni-ui/uni-nav-bar/uni-nav-bar.vue';
export default {
	components: {
		uniNavBar
	},
	data() {
		return {
			tabIndex: 0, //当前选中第一个
			scrollInto: '',
			scrollH: 600, //列表高度默认
			tabBar: [
				{ name: '关注' },
				{ name: '推荐' },
				{ name: '抗击肺炎' },
				{ name: '广东' },
				{ name: '体育' },
				{ name: '热点' },
				{ name: '财经' },
				{ name: '娱乐' },
				{ name: '军事' },
				{ name: '历史' },
				{ name: '本地' }
			],
			newsList: []
		};
	},
	onLoad() {
	
		// 页面进来获取高度
		uni.getSystemInfo({
			success: res => {
				console.log(res)
				// 获取的是px单位 转换为upx
				this.scrollH = res.windowHeight*2 - 205;
			}
		});
	},
	methods: {
		// 切换选项
		changeTab(index) {
			if (this.tabIndex === index) {
				return;
			}
			this.tabIndex = index;
			// 滚动到指定元素
			this.scrollInto = 'tab' + index;
			console.log(this.scrollInto)
		},
		// 监听滑动 上下关联
		onChangeTab(e) {
			console.log(e)
			this.changeTab(e.detail.current);
		}
	}
};
</script>

<style scoped>
</style>
