# 实时猫 JS SDK | RealTimeCat JavaScript SDK  

## 关于

实时猫 JS SDK是实时猫客户端库的一部分，实时猫客户端库的主要目的是通过对连接实时猫云WebRTC服务器功能的封装，大大简化开发实时交互应用的难度，并可以使用实时猫提供的高级WebRTC功能。

开发者通过实时猫JS SDK，可以进行Web端的实时视频开发。

## 下载实时猫 JS SDK

选择以下方式中的任意一种加载实时猫 JS SDK。

### 直接使用实时猫CDN

通过引入CDN上的实时猫JavaScript文件，可以直接在页面内加载实时猫JavaScript SDK。

新建一个HTML网页，在网页的```<head>```和```</head>```之间，添加以下代码：
    
```html
<!-- 加载实时猫 JavaScript SDK -->
<script src="https://cdn.realtimecat.com/realtimecat/realtimecat-0.4.0.min.js"></script>
```

### 使用包管理软件加载实时猫SDK

如果使用Bower作为包管理器，直接运行以下命令安装实时猫JavaScript SDK：

```bash
$ bower install realtimecatjs#0.4.0 --save
```

如果使用NPM，直接运行以下命令安装：

```bash
$ npm install realtimecatjs --save
```

在使用包管理软件安装完成后，仍需要在具体HTML页面中，引入下载好的实时猫JavaScript SDK。

本SDK同时符合AMD和CommonJS的规范，你可以通过RequireJS或者`require('realtimecatjs')`的方式来调用实时猫JavaScript SDK。

## Changelog

v0.4

增加方法：

- 增加`Mos`平均主观意见评分
- 增加用户内部测试的服务器`Relay`模式
- 增加 LocalStream.release() 方法，用于回收本地流资源。
- 增加 RTCat.detect() 用于测试浏览器兼容性和网速。

增加事件：

```
Sender:
sender.on('file_channel_open') 发文件通道打开
sender.on('file_channel_close') 发文件通道关闭
sender.on('file_channel_error') 发文件通道出错

Receiver:
receiver.on('file_channel_open') 发文件通道打开
receiver.on('file_channel_close') 发文件通道关闭
receiver.on('file_channel_error') 发文件通道出错
```


更改方法:

- 将 `Stream` 分为 本地流 `LocalStream` 和 远程流 `RemoteStream` , 本地流和远程流继承 抽象流 `AbstractStream`
- 修改`LocalStream`构造函数
- 修改`Session`构造函数
- stream.stop方法只回收播放器,可以用play方法重新播放，回收本地流资源需使用`LocalStream.release`方法

更改事件：

```
LocalStream:
stream.on('access-accepted') -> stream.on('accepted')
stream.on('access-failed') -> stream.on('error')


Session:
session.on('send_error') -> session.on('error')
session.on('connect_error') -> session.on('error')
session.on('channel_error') -> session.on('error')

Sender:
sender.getReceiver() -> sender.getReceiverToken()
sender.attr -> sender.getAttr()
sender.on('file_sending_error') -> sender.on('error')
sender.on('send_error') -> sender.on('error')
sender.on('sender_connect_error') -> sender.on('error')
sender.on('dataChannel_error') -> sender.on('channel_error')
sender.on('dataChannel_close') -> sender.on('channel_close')
sender.on('dataChannel_open') -> sender.on('channel_open')

Receiver:
receiver.getSender() -> receiver.getSenderToken()
receiver.attr -> receiver.getAttr()
receiver.on('receiver_connect_error') -> receiver.on('error')
receiver.on('dataChannel_error') -> receiver.on('channel_error')
receiver.on('dataChannel_close') -> receiver.on('channel_close')
receiver.on('dataChannel_open') -> receiver.on('channel_open')
```

移除方法：

- 移除 LocalStream.getCapture()


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
