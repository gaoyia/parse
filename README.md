## uParse 更新说明

# uParse-提问反馈交流群 83254601【非uniapp官方】，目前需要除了微信支付宝小程序以外的小伙伴帮忙测试，和远程调试

# 暂时请勿从 npm安装，未维护

1.1.1

* 删除p标签的padding-bottom: -1em;   ps:想了想还是不能用一个bug修复另一个bug，有需求的自己改
* 通过条件编译判断，如果是APP和H5则使用组件递归，小程序则用多个组件方式渲染html，解决部分平台html层级较深无法渲染问题
* 修复了小程序表格没有css的问题，感谢plfqz
* 给a标签增加了attr获取，例如：获取 onclick="void(0)"
* 修复了html中多个空格的问题 （css增加了white-space: pre-wrap，修剪了text节点的左右两端空白字符串）
* 目前测试上下标emoji正常

> 本组件修复自官方uParse

* 修复了组件中添加空白view的情况
* 修复了引入样式的的文档错误
* 修复了表格无法正确解析的问题。
* 优化了一些css样式
* 再次强调一下->建议HBuilderX升级到1.9+，在manifest.json配置"usingComponents": true, 且对整个项目完整测试!

## uParse 适用于 uni-app/mpvue 的富文本解析组件

> 支持 Html、Markdown 解析，Fork自: [mpvue-wxParse](https://github.com/F-loat/mpvue-wxParse)

## 对于某些html标签不闭合等渲染有问题的
，如果是PHP推荐结合[https://github.com/phith0n/XssHtml](https://github.com/phith0n/XssHtml)使用
 $this->m_dom = new DOMDocument();
 
## 属性

| 名称             | 类型          | 默认值        | 描述               |
| -----------------|--------------- | ------------- | ----------------  |
| userSelect       | String         | text          | none,text,all,element是否可选可复制|
| imgOptions       | Object         | 参照组件源码和uni.previewImage文档| 把previewImage的选项拿出来|
| loading          | Boolean        | false         | 数据加载状态       |
| className        | String         | —             | 自定义 class 名称  |
| content          | String         | —             | 渲染内容           |
| noData           | String         | 数据不能为空   | 空数据时的渲染展示  |
| startHandler     | Function       | 见源码         | 自定义 parser 函数 |
| endHandler       | Function       | null          | 自定义 parser 函数 |
| charsHandler     | Function       | null          | 自定义 parser 函数 |
| imageProp        | Object||Boolean         | 见下文        | 图片相关参数，当属性为任意布尔值时取消图片点击事件|

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
        article: '<p>html代码，具体参见https://github.com/gaoyia/parse/tree/1.0.7/parse-demo中的demo</p>'
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
    },
	/* 支付宝小程序特有配置 */  
	"mp-alipay" : {
	    "usingComponents" : true
	},
	/* 百度小程序特有配置 （由于没有开发者账号，暂未测试）*/
	"mp-baidu" : {
	    "usingComponents" : true
	}
}  
```