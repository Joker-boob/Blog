---
title: js中使用防抖和节流
tags: [js,前端]
categories: JS
cover: https://th.bing.com/th/id/R.fc32f16276c6e6459d579924c0456e11?rik=2K8yVgHO12Is6w&riu=http%3a%2f%2f3.bp.blogspot.com%2f-PTty3CfTGnA%2fTpZOEjTQ_WI%2fAAAAAAAAAeo%2fKeKt_D5X2xo%2fw1200-h630-p-k-nu%2fjs.jpg&ehk=2PrB9111t3zKW%2f42wxMGGN6YYYRN3%2bgtuPOWner1T8M%3d&risl=&pid=ImgRaw&r=0
top_img: https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2022/11/24/14/12171669270661640.webp
---

<a name="jaSFv"></a>

## 为什么使用防抖节流

打开控制台复制以下代码 然后回车 然后滚动页面，可见随便滚动一下，就会有好多条输出，也就是说这个函数的
执行频率很高，随便动一下就会执行很多次，但是我们并不需要如此高的执行频率，浏览器的性能也是有限的。

```javascript
window.onscroll = function(){
  var scrollTop = document.body.scrollTop || document.documentElement.scrollTop;
　console.log('滚动条位置：' + scrollTop);
}
```

<a name="ndYib"></a>

## 防抖（debounce）

```javascript
let setDebounce = (fun, time = 3000) => {
  let timer = null;
  return function () {
    if (timer) {
      clearTimeout(timer)
    }
    timer = setTimeout(() => {
      fun.apply(this, arguments);
    }, time)
  }
}
```

<a name="mUwPg"></a>

## 节流(Throttle)

```javascript
let setThrottle = (fun, time = 3000) => {
  let state = true;
  return function () {
    if (!state) {
      return;
    }
    state = false;
    fun.apply(this, arguments);
    setTimeout(() => {
      state = true;
    }, time)
  }
}
```
