<template>
	<view class="content">
		<text>  fdafdafdafdsa
		
		fdafdsafdsa
		fasd</text>
			<view @click="load()">加载数据</view>
			<br>
			<view @click="unload()">卸载数据</view>
			<br>
			
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
				detailData: '<p><span style="font-size:28px"><span style="line-height:1.75"><span style="letter-spacing:2px">大威德群奥多</span></span></span></p>',
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
				this.detailData = ``
			},
			load(){
				this.detailData = `
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
