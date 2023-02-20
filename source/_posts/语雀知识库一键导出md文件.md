---
title: 语雀知识库一键导出md文件
date: 2023-02-20 10:40:43
top_img: https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2011%3A23%3A251676863404940.png
cover: https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2011%3A23%3A251676863404940.png
categories: 工具
---
1. 获取个人开发者的Token传送门->https://www.yuque.com/settings/tokens

   点击新建

   ![](https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2010%3A57%3A261676861846597.png)

   选择授权范围 填写用途



![](https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2010%3A59%3A471676861987649.png)

复制这里的token

![](https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2011%3A00%3A521676862052421.png)

然后打开控制台输入以下代码：

```cpp
npm i -g yuque-exporter --registry=https://registry.npmmirror.com
SET YUQUE_TOKEN=刚刚复制的token yuque-exporter
yuque-exporter 语雀账号//yuque-exporter joker-3bqs9
```

![](https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2023-2-20%2011%3A23%3A251676863404940.png)

执行如上代码时候，如发生超时  多执行几次就ok

根据提示就可以找到导出的文件  可能发发现图片路不对  参考传送门:https://blog.csdn.net/qq_42445757/article/details/124843848
