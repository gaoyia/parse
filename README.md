
## uParse 修复说明
1.0.7

* 修复了uParse外部有边距的情况图片高度不正确的问题
* 添加默认选项，长按可选择复制文字
* 简单粗暴的暴露出图片浏览器的配置选项

1.0.6
* 修改文档
* 首次提交npm并未测试，如有错误请大佬请给出修改建议

1.0.5 

* 由于需要配置npm名称，又改名了，各位老用户对不住了
* 添加了git和npm项目地址
* 段落字体大小改为1em
* 给图片添加了display:block;修复了在段落中有text-indent的时候图片也缩进的问题

1.0.3
* 修复h1~h6标签无法添加样式的问题

1.0.1版
  发现问题：
* h1~h6标签无法添加样式

> 本组件修复自官方uParse

* 修复了组件中添加空白view的情况
* 修复了引入样式的的文档错误
* 修复了表格无法正确解析的问题。
* 优化了一些css样式
* 再次强调一下->建议HBuilderX升级到1.9+，在manifest.json配置"usingComponents": true, 且对整个项目完整测试!

## uParse 适用于 uni-app/mpvue 的富文本解析组件

> 支持 Html、Markdown 解析，Fork自: [mpvue-wxParse](https://github.com/F-loat/mpvue-wxParse)


## 属性

| 名称             | 类型          | 默认值        | 描述               |
| -----------------|--------------- | ------------- | ----------------  |
| userSelect       | String         | text          | none,text,all,element是否可选可复制|
| imgOptions       | Object         | 参照组件源码和uni.previewImage文档| 把previewImage的选项拿出来|
| parseName        | String         | wxParse       | 定义parse的class-name|
| loading          | Boolean        | false         | 数据加载状态       |
| className        | String         | —             | 自定义 class 名称  |
| content          | String         | —             | 渲染内容           |
| noData           | String         | 数据不能为空   | 空数据时的渲染展示  |
| startHandler     | Function       | 见源码         | 自定义 parser 函数 |
| endHandler       | Function       | null          | 自定义 parser 函数 |
| charsHandler     | Function       | null          | 自定义 parser 函数 |
| imageProp        | Object         | 见下文        | 图片相关参数        |

### 自定义 parser 函数具体介绍

* 传入的参数为当前节点 `node` 对象及解析结果 `results` 对象，例如 `startHandler(node, results)`
* 无需返回值，通过对传入的参数直接操作来完成需要的改动
* 自定义函数会在原解析函数处理之后执行

### imageProp 对象具体属性

| 名称              | 类型           | 默认值        | 描述                |
| -----------------|--------------- | ------------- | ------------------ |
| mode             | String         | 'aspectFit'   | 图片裁剪、缩放的模式 |
| padding          | Number         | 0             | 图片内边距          |
| lazyLoad         | Boolean        | false         | 图片懒加载          |
| domain           | String         | ''            | 图片服务域名        |

## 事件

| 名称             | 参数              | 描述              |
| -----------------|----------------- | ----------------  |
| preview          | 图片地址，原始事件 | 预览图片时触发     |
| navigate         | 链接地址，原始事件 | 点击链接时触发     |

## 基本使用方法


``` vue
<template>
  <div>
    <u-parse :content="article" @preview="preview" @navigate="navigate" />
  </div>
</template>

<script>
import uParse from '@/components/gaoyia-parse/parse.vue'

export default {
  components: {
    uParse
  },
  data () {
    return {
        article: `
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
			<img src="https://res.wx.qq.com/mpres/en_US/htmledition/vue-weui/src/weui-desktopSkin/svg/buildless/bg_logo_primary45cbf6.svg">
	    `
    }
  },
  methods: {
    preview(src, e) {
      // do something
    },
    navigate(href, e) {
      // do something
    }
  }
}
</script>

//在APP.vue中引入，否则样式不能生效
<style>
@import url("/components/gaoyia-parse/parse.css");
</style>
```


## 渲染 Markdown

> 先将 markdown 转换为 html 即可

```
npm install marked
```

``` js
import marked from 'marked'
import uParse from '@/components/gaoyia-parse/parse.vue'

export default {
  components: {
    uParse
  },
  data () {
    return {
      article: marked(`#hello, markdown!`)
    }
  }
}
```

> 建议HBuilderX升级到1.9+，在manifest.json配置"usingComponents": true, 且对整个项目完整测试

``` json
// manifest.json  
{  
    // ...  
    /* App平台特有配置 */  
    "app-plus": {
        "usingComponents":true  
    }  
    /* 微信小程序特有配置 */  
    "mp-weixin": {
        "usingComponents":true
    }  
}  
```