<template>
	<view class="content" >
		<text>  fdafdafdafdsa
		
		fdafdsafdsa
		fasd</text>
			<view @click="load()">加载数据2</view>
			<br>
			<view @click="unload()">卸载数据</view>
			<br>
			<view v-if="test">
				<u-parse :content="detailData" :loading="loading" @preview="preview" @navigate="navigate" />
			</view>
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
				test:false,
				detailData: '<p></p>',
				loading:false//开启loading不显示默认值
			}
		},
		onLoad() {
			
			setTimeout(()=>{
				this.load()
				// this.loading = false;
			},2000)
		},
		methods: {
			preview(src, e) {
			  // do something
			},
			navigate(href, e) {
			  // do something
			},
			unload(){
				this.test = false
				this.detailData = ``
			},
			load(){
				this.test = true
				this.detailData = `
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
	<h1>H1</h1>
	<h2>H2</h2>
	<h3>H3</h3>
	<h4>H4</h4>
	<h5>H5</h5>
    <h6>H6</h6>
    <br>换行<br>
    <i>iii</i>
    <em>em</em>
    <strong>strong</strong>
    <b>bbb</b>
    <del>del</del>
    <u>uuu</u>
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
	<h3>下面是两张连在一起的图片，就算在p标签内也会把图片拼接在一起。比如某些商品详情图片都是拼接在一起的</h3>
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
				<img src="https://www.baidu.com/img/baidu_jgylogo3.gif"/>
				1&nbsp;&nbsp;&nbsp;1
				<p>2&nbsp;&nbsp;&nbsp;2</p>
				<code>{
	"code": 200,
    "msg": "success",
    "data": {
	"id": 80,
	"shorttitle": "最值得入手的运动鞋",
	"title": "2019年流行这几双运动鞋，款款都好看",
</code>
<table border="1">
<tr>
  <th>姓名</th>
  <th>电话</th>
  <th>电话</th>
  <th>电话</th>
  <th>电话</th>
  <th>电话</th>
  <th>电话</th>
  <th>电话</th>
</tr>
<tr>
  <td>Bill Gates</td>
  <td>555 77 854</td>
  <td>555 77 855</td>
  <td>555 77 855</td>
  <td>555 77 855</td>
  <td>555 77 855</td>
  <td>555 77 855</td>
  <td>555 77 855</td>
</tr>
</table>
<p>
这里有很多空格的实体<br>
&nbsp;|&#32;|&#x20;<br>
&ensp;|&#8194;|&#x2002;<br>
&#12288;|&#x3000;<br>
&emsp;|&#8195;|&#x2003;<br>
&quot;|&#34;|&#x22;<br>
&quot;|&#39;|&#x27;<br>
&acute;|&#180;|&#xB4;<br>
&times;|&#215;|&#xD7;<br>
&divide;|&#247;|&#xF7;<br>
&amp;|&#38;|&#x26;<br>

大于小于号会被渲<font>染成标签</font>:目前无好的办法,求<strong>解题思路</strong>,下面有个br的换行
&lt;|&#60;|&#x3c;br
&gt;|&#62;|&#x3e;<br>
</p>
				<pre>55&hearts;|&#9829;|&#x2665;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;77777777777777777777777777777777777777777777777755</pre>
				
				
				
		
<h1><a name="docker-swarm安装配置说明" class="md-header-anchor"></a><span>Docker Swarm安装配置说明</span></h1><h2><a name="环境信息" class="md-header-anchor"></a><span>环境信息</span></h2><ul><li><span>CentOS Linux release 7.4.1708 (Core)</span></li><li><span>Docker 18.03.1-ce</span></li></ul><h2><a name="1docker安装" class="md-header-anchor"></a><span>1.docker安装</span></h2><p><span>1.Install required packages. yum-utils provides the yum-config-manager utility, and device-mapper-persistent-data and lvm2 are required by the devicemapper storage driver.</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">yum install -y yum-utils \</span></pre></div></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"></div><div class="CodeMirror-gutters" style="display: none; height: 23px;"></div></div></div></pre><p><span>  </span><span>	</span><span>device-mapper-persistent-data \</span>
<span>  </span><span>	</span><span>lvm2</span></p><p><span>2.Use the following command to set up the stable repository.</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">yum-config-manager \</span></pre></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">--add-repo \</span></pre><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">https://download.docker.com/linux/centos/docker-ce.repo</span></pre></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 69px;"></div><div class="CodeMirror-gutters" style="display: none; height: 69px;"></div></div></div></pre><p><span>3.Install the latest version of Docker Engine - Community and containerd</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">yum install docker-ce docker-ce-cli containerd.io</span></pre></div></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"></div><div class="CodeMirror-gutters" style="display: none; height: 23px;"></div></div></div></pre><p><span>4.Start Docker.</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">systemctl start docker</span></pre></div></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"></div><div class="CodeMirror-gutters" style="display: none; height: 23px;"></div></div></div></pre><p><span>5.Test Docker.</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">docker run hello-world</span></pre></div></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"></div><div class="CodeMirror-gutters" style="display: none; height: 23px;"></div></div></div></pre><p><span>6.use Docker as a non-root user</span></p><pre spellcheck="false" class="md-fences md-end-block ty-contain-cm modeLoaded" lang=""><div class="CodeMirror cm-s-inner CodeMirror-wrap" lang=""><div style="overflow: hidden; position: relative; width: 3px; height: 0px; top: 0px; left: 8px;"><textarea autocorrect="off" autocapitalize="off" spellcheck="false" tabindex="0" style="position: absolute; bottom: -1em; padding: 0px; width: 1000px; height: 1em; outline: none;"></textarea></div><div class="CodeMirror-scrollbar-filler" cm-not-content="true"></div><div class="CodeMirror-gutter-filler" cm-not-content="true"></div><div class="CodeMirror-scroll" tabindex="-1"><div class="CodeMirror-sizer" style="margin-left: 0px; margin-bottom: 0px; border-right-width: 0px; padding-right: 0px; padding-bottom: 0px;"><div style="position: relative; top: 0px;"><div class="CodeMirror-lines" role="presentation"><div role="presentation" style="position: relative; outline: none;"><div class="CodeMirror-measure"><pre><span>xxxxxxxxxx</span></pre></div><div class="CodeMirror-measure"></div><div style="position: relative; z-index: 1;"></div><div class="CodeMirror-code" role="presentation"><div class="CodeMirror-activeline" style="position: relative;"><div class="CodeMirror-activeline-background CodeMirror-linebackground"></div><div class="CodeMirror-gutter-background CodeMirror-activeline-gutter" style="left: 0px; width: 0px;"></div><pre class=" CodeMirror-line " role="presentation"><span role="presentation" style="padding-right: 0.1px;">usermod -aG docker your-user</span></pre></div></div></div></div></div></div><div style="position: absolute; height: 0px; width: 1px; border-bottom: 0px solid transparent; top: 23px;"></div><div class="CodeMirror-gutters" style="display: none; height: 23px;"></div></div></div></pre><h2><a name="2swarm安装" class="md-header-anchor"></a><span>2.swarm安装</span></h2><blockquote><p><span>注：需要docker 1.12以上</span></p></blockquote><table>
    <tbody><tr>
        <th>主机名</th>
        <th>IP</th>
        <th>角色</th>
    </tr>
    <tr>
        <td>manager1</td>
        <td>192.168.1.1</td>
        <td>swarm manager</td>
    </tr>
    <tr>
        <td>worker1</td>
        <td>192.168.1.2</td>
        <td>swarm worker</td>
    </tr>
    <tr>
        <td>worker2</td>
        <td>192.168.1.3</td>
        <td>swarm worker</td>
    </tr>
</tbody></table>
				`
			}
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
