# Hi头像

让头像有趣一点

## 核心亮点

* 基于腾讯云云开发开发，易部署、扩展性很好，核心配置已进行抽离
* 基于 Taro 打造，有微信小程序端和 Web 端，将来还可以扩展更多端
* 用户体验好，易于操作，交互动画友好且动感
* 独家拥有技术小册《**[从0到1开发一个智能头像识别小程序](https://www.xiaoxili.com/hi-face/docs/README.html)**》，详细说明 Hi 头像主要实现思路


## 功能体验

小程序二维码

![](https://image-hosting.xiaoxili.com/img/img/20200911/6f53bfa6573da16bec899f169fe58ae4-977c15.png)

Web 体验版：[https://face.xiaoxili.com](https://face.xiaoxili.com)

## 愿景

### 使用场景&目标用户&背景

在节日的时候，我们可以使用符合节日七夕的头像，比如在国庆节使用含国旗的头像表达对祖国的祝福；在圣诞节的时候，我们能给亲朋送一个带圣诞帽的头像传递快乐。

### 需求分析

在一些特定节日里，很多人尤其是年轻人喜欢新潮的头像，比如近几年的圣诞节，会有“@官方微信，送我一顶圣诞帽“的需求，对此，我们做这个小程序，来解决特定时候头像的制作。

### 设计理念

**标语：让头像有趣一点**

「Hi头像」结合节日特点，微信头像进行智能化处理，让头像更加符合节日氛围。

1、紧跟节日热点

国庆节头戴国旗、圣诞节智能戴帽子，增加节日乐趣

2、简单易操作

不同于各类app的繁琐，小程序更简洁易操作

3、乐于分享

借助微信社交机制，头像处理后可以分享给好友或分享到朋友圈，展示头像成果

### 用户画像

20-35喜欢分享的年轻人


### 作品效果图
![](https://image-hosting.xiaoxili.com/img/img/20200911/5647e3ce1d5e7a80ddf51101915775e0-3ae655.png)


## 主创人员

**小溪里，技术研发**

个人网站：[https://www.xiaoxili.com](https://www.xiaoxili.com)

公众号：小溪里


**不二雪，UI设计**

<!-- 作品集地址：待补充 -->

公众号：不二诗旅

## 部署文档

本项目的部署文档非常详细，详情请查看《[DEPLOYMENT](https://github.com/hi-our/hi-face/blob/master/DEPLOYMENT.md)》文档。

## 学习资源

《**[从0到1开发一个智能头像识别小程序](https://www.xiaoxili.com/hi-face/docs/README.html)**》

>本技术小册基于Hi 头像 v1版本编写，v2 版本正在撰写中。

从产品功能规划、技术选型到实战开发，全方位介绍基于小程序云开发来实现智能人像识别小程序，不仅能完成跨端开发，更能学习到当今炙手可热的 ServerLess 开发实战（即小程序与 Web 云开发），更能将高深的人工智能技术落地到真实项目中，甚至，我们还将探索如何将小程序与Web端完成前端工程化实践。

**你会学到什么？**

* 小程序云开发配置与开发技巧，亲历云开发的实战场景
    * 基于 tcb-router 封装多功能的 API 服务
    * 基于静态网站托管部署 Web 版
    * 基于 CMS 内容管理系统来统一管理数据
    * 基于 Cloudbase-Framework 来部署云函数、小程序和 Web 端
* 体验及实战腾讯云人工智能特色功能，如人脸识别、五官分析、人像转换等
* Taro 跨端使用技巧，在实战中了解Canvas在小程序与web端的差异，以及图片裁剪、压缩、上传的各种技术细节
* 产品需求、项目规划的实战知识
## 项目综述

本项目在小程序和Web端使用 Taro 构建，功能服务基于[腾讯云云开发](https://www.cloudbase.net/)及腾讯云人工智能服务，使用 CMS 内容管理系统来管理数据，基于[Cloudbase Framework](https://github.com/TencentCloudBase/cloudbase-framework)完成小程序端、Web端、云函数端构建。

### 整体关系图

![](https://image-hosting.xiaoxili.com/img/img/20200911/ba367852e79f4acfcbc15855adca3545-3ed2a1.png)

### 页面间调用关系图

在`taro/src`中，有以下文件

```
|-config.js 配置AppId、云环境Id及其它
|-components 全局组件
|-pages
|-|- avatar-edit 头像编辑页
|-|- avatar-poster 头像分享页
|-|- theme-list 主题列表
|-|- self 我的，含个人头像列表
```

![](https://image-hosting.xiaoxili.com/img/img/20200911/8eac43d66cafebcdd0eb76042f414572-e11a3a.png)

### 头像编辑页流程图

头像编辑是Hi 头像的主逻辑，下面这个流程图充分展示了从加载主题数据、到头像编辑、再到头像生成的完整流程。

Hi 头像功能以小程序端为主，功能齐全，而在 web端能制作头像并保存图片，暂不提供头像保存和分享功能。

![](https://uploader.shimo.im/f/x2wUY5DvXrLBHuWs.png!thumbnail)

### 五官分析时序图

v1版中使用图示“第五版”时序图来完成主逻辑，而v2版中使用“第六版”时序图，这两者差异点就是基于已有服务来完成功能，更容易初学者掌握。

![](https://images-cdn.shimo.im/x2wUY5DvXrLBHuWs__thumbnail.png)

### 核心语法

1、云函数`hiface-api`基于`tcb-router`做路由跳转

主要功能有头像、主题、用户信息的获取与更新，还有创建小程序码的功能。

路径为`cloud/functions/hiface-api`

2、核心算法

基于五官分析为多个人脸戴上贴纸，具体可以查看《[通过五官分析实现为人脸佩戴贴纸](https://www.xiaoxili.com/hi-face/docs/4-development/3-analyze-face-shape.html)》