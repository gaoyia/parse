<template>
	<view class="content">
		<u-parse :content="detailData" :loading="loading" @preview="preview" @navigate="navigate" />
	</view>
</template>
<script>
	import uParse from '@/components/gaoyia-parse/parse.vue'

	export default {
		components:{
			uParse
		},
		data() {
			return {
				detailData: '正在加载数据，模拟网络延迟2秒😝',
				loading:false//开启loading不显示默认值
			}
		},
		onLoad() {
			let that = this;
			setTimeout(function(){
				that.detailData = `
				正常<sup>上标</sup><br /> 
				正常<sub>下标</sub><br /> 
					emoji😝<br /> 
					<table border="1">
					  <thead>
						<tr>
						  <th>表头1</th>
						  <th>表头2</th>
						</tr>
					  </thead>
					  <tbody>
						<tr>
						  <td>body1</td>
						  <td>body2</td>
						</tr>
						<tr>
						  <td>body3</td>
						  <td>body4</td>
						</tr>
					  </tbody>
					  <tfoot>
						<tr>
						  <td>tfoot1</td>
						  <td>tfoot2</td>
						</tr>
					  </tfoot>
					</table>
					<a href='https://www.baidu.com' onclick='void(0)'>a标签</a>
					<br>换行的中 间  有       几个空格<br>
					<i>iii</i><br>
					<em>em</em><br>
					<strong>strong</strong><br>
					<b>bbb</b><br>
					<del>del</del><br>
					<u>uuu</u><br>
					<p>
						ppp
						<span>span</span>
						ppp
					</p>
					<p>
						这是两个连在一起的段落，P标签之间有段落间距。~~~~~~~~~这是两个连在一起的段落，P标签之间有段落间距。
					</p>
					<p>
						这是两个连在一起的段落，P标签之间有段落间距。~~~~~~~~~这是两个连在一起的段落，P标签之间有段落间距。
					</p>
					
					<hr>
					
					<p>
						<img src="https://cdn.multilingualres.hr.tencent.com/careersmlr/cityinfo_sz2.jpg">
					</p>
					<p>
						<img src="https://cdn.multilingualres.hr.tencent.com/careersmlr/cityinfo_sz3.jpg">
					</p>
					<p>
						<img src="https://cdn.multilingualres.hr.tencent.com/careersmlr/cityinfo_sz4.jpg" style="padding-left:10px">
					</p>
					<h3>上面是一张自带padding的图片，，感觉还有些小问题后续需要调整</h3>
					<ol>
						<li>li1</li>
						<li>li2</li>
						<li>li3</li>
					</ol>
					<ul>
						<li>li1</li>
						<li>li2</li>
						<li>li3</li>
					</ul>
					<audio src="https://img-cdn-qiniu.dcloud.net.cn/uniapp/audio/music.mp3">
					您的浏览器不支持 audio 标签。
					</audio>
					<video src="https://dcloud-img.oss-cn-hangzhou.aliyuncs.com/guide/uniapp/%E7%AC%AC1%E8%AE%B2%EF%BC%88uni-app%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D%EF%BC%89-%20DCloud%E5%AE%98%E6%96%B9%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B@20181126.mp4">
					您的浏览器不支持 audio 标签。
					</video>
					<h1>H1</h1>
					<h2>H2</h2>
					<h3>H3</h3>
					<h4>H4</h4>
					<h5>H5</h5>
					<h6>H6</h6>
				`
				that.loading = false;
			},3000)
		},
		methods: {
			preview(src, e) {
			  // do something
			},
			navigate(href, e) {
			  // do something
			},
		}
	}
</script>
<style>
	.content {
		padding-left: 1.5em;
		padding-right: 1.5em;
		/* 在这里调整，整体字体大小 */
		font-size: 35upx;
	}
</style>
