# 开篇

在开始本篇教程前, 我希望你有

- 至少一门编程语言基础
- 至少了解过一丢丢`http`
- ..

需要申明的是,本篇文,主要面向前端, 并且我所讲的`api`是有一定"歧义"的
(欢迎提`issues`讨论)

以下是目录

- [`api`是什么鬼]
  - [基本概括](#基本概括)

- [Ajax]
  - [demo](#ajax-demo)
  - [跨域到底怎么解决?](#CORS)

- [一些小例子](#demo)

- [结束语](#over)


## 基本概括

> API（Application Programming Interface，应用程序编程接口）是一些预先定义的函数，目的是提供应用程序与开发人员基于某软件或硬件得以访问一组例程的能力，而又无需访问源码，或理解内部工作机制的细节。

通俗一点的来说, 我们现在写的代码都是撸的别人写好的`API`, 我们去调用, 我们都知道, 在`浏览器`中有`DOM`对象, `DOM`最顶层有`window`对象

```js

window.isDev = document.title == 'dev'

```

我们不需要在意这些接口是怎么实现的,本篇文章不会去教你去写一个`接口`, 而是**教你如果去使用别人的接口**

## Ajax

> Ajax 即“Asynchronous Javascript And XML”（异步 JavaScript 和 XML），是指一种创建交互式网页应用的网页开发技术。

这里有一个误区需要跟大家去啰嗦一下: ** AJAX ** 是一个技术名词。

话不多说, 直接给大家上代码

```js
var url = 'https://baidu.com'
$.ajax({
  url: url,
  success: function(data) {
    console.log(data)
  }
})

// 2.0 版本

const ajax = ()=> new Promise((rcv, rjt)=> {
  fetch(url)
   .then(r=>r.json)
   .then(r=> {
     rcv(r)
   })
   .catch(err=> {
     console.error(err)
     rjt(err)
   })
})

```

`$.ajax`方法就不多说了吧, 


### 跨域到底怎么解决?

跨域是`web`开发最常遇到的问题, 解决方法不一, 但是解决思路无外乎就是两种:

- 前端客户端
- 后端设置请求头

详情可以[猛戳这里](./docs/cors.md)


### 一些小例子

没有下一位..


### 结束语

你是真的水😪啊, 无奈自己水平有限, 不能够很好的表达出来, 并且也不知道你们的所需, 如果可以的话, 请务必在`issues`中留言你需要看到的内容或教程,谢谢.

-- 以上致敬: @luxizhizhong 项目组(`@d1y` 2019-10-03)
