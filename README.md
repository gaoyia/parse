## uParse 更新说明

## uParse-提问反馈交流群 83254601【非uniapp官方】

1.2.0 修复了一些历史遗留问题

关于组件的一些说明

[关于组件的一些说明：https://ask.dcloud.net.cn/article/36531](https://ask.dcloud.net.cn/article/36531)

> 本组件修复自官方uParse

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