# 实时猫 JS SDK | RealTimeCat JavaScript SDK  

## 关于

实时猫 JS SDK是实时猫客户端库的一部分，实时猫客户端库的主要目的是通过对连接实时猫云WebRTC服务器功能的封装，大大简化开发实时交互应用的难度，并可以使用实时猫提供的高级WebRTC功能。

开发者通过实时猫JS SDK，可以进行Web端的实时视频开发。

此版本实时猫JS SDK为处于测试发布阶段的v0.4 alpha版。

## 下载实时猫 JS SDK

选择以下方式中的任意一种加载实时猫 JS SDK。

### 直接使用实时猫CDN(暂不可用)

通过引入CDN上的实时猫JavaScript文件，可以直接在页面内加载实时猫JavaScript SDK。

新建一个HTML网页，在网页的```<head>```和```</head>```之间，添加以下代码：
    
```html
<!-- 加载实时猫 JavaScript SDK -->
<script src="https://cdn.realtimecat.com/realtimecat/realtimecat-0.3-alpha.min.js"></script>
```

### 使用包管理软件加载实时猫SDK

如果使用Bower作为包管理器，直接运行以下命令安装实时猫JavaScript SDK：

```bash
$ bower install realtimecatjs#0.4.0-alpha.1 --save
```

如果使用NPM，直接运行以下命令安装：

```bash
$ npm install realtimecatjs@next --save
```

在使用包管理软件安装完成后，仍需要在具体HTML页面中，引入下载好的实时猫JavaScript SDK。

本SDK同时符合AMD和CommonJS的规范，你可以通过RequireJS或者`require('realtimecatjs')`的方式来调用实时猫JavaScript SDK。

## Changelog

v0.4

待添加

v0.3

增加 Relay 模式 (私有云用户内测中，目前公有云用户不可使用)
移除 RTCat.Detect 模块

修复以下 Bug

修复和Android端连接时，Android端无音视频问题
修复 Firefox 部分不兼容问题

0.2.8 修复stream.stop()方法的bug

0.2.7 修复只请求音频时，video placeholder的地址

0.2.6 修复只请求音频时视频被强制带上的bug

0.2.5 修复mute方法无效的bug

0.2.4 使用umd规范打包SDK，增加对AMD和CommonJS规范的支持

0.2.3 增加监听事件的once方法，监听的事件只触发一次

0.2.2 修复stream.play()方法只传width或height时，另一方为undefined的bug

## 相关资源

- 实时猫官方网站：https://shishimao.com
- 开发者中心：https://shishimao.com/developer-center
- 技术演示：https://shishimao.com/rooms
- Dashboard：https://dashboard.shishimao.com/
- 0.4版JS SDK在线文档地址: [http://rtc-docs.readthedocs.io/zh_CN/latest/03.%20web.html](http://rtc-docs.readthedocs.io/zh_CN/latest/03.%20web.html)
