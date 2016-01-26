---
layout:     post
title:      "React Native实践"
subtitle:   "There is no such thing as a great talent without great will - power."
date:       2016-01-10 12:00:00
author:     "bu he"
header-img: "img/post-bg-02.jpg"
---

##简介
今年的当红炸子鸡，后端是docker，mesos，前端就是React Native了。
我前6年的职业生涯主要集中在backend，基本上跟大多数后端同学差不多，在填大数据，高并发，数据分析这几个坑。
从去年开始离开公司在家Zen和做一些不怎么叫座的项目打发日子，今年在头脑中孵化了一个还不错的项目准备开始认真做起来。
在前端选型上肯定选择效率比较高的选择，但是又害怕RN在功能实现上和App Store上有政策问题，先和朋友合作开发了一款
App验证RN在实际项目中的效果。
废话不多说，因为这是一款国内的App，而且没有盈利点，所以用了很多免费的云端服务。

##云服务
[leancloud](http://leancloud.cn) ,国内做的比较成熟的BaaS，我原来的公司就是做类似项目的，我也是那个项目的负责人
之一，其实对类似的服务还比较有感情，知道大家日子过的一般。leancloud在月百万API以下是免费的。
[JS SDK](https://github.com/leancloud/javascript-sdk/tree/v1.0.0-rc5)库也支持了RN，
他们Team的效率和动作都挺快，技术嗅觉很赞。
目前还有一些集成问题，如[Push notification](https://github.com/leancloud/javascript-sdk/issues/215)。
但整体感觉还是很顺畅的。另外用了他们短信服务，到达率挺高的，SDK写的也很赞，我也已经付过费，非常感谢。


##网络框架
网络框架用了浏览器上常用的superagent，其实和fetch api也差不多，但是用这个好处就是在所有端都可以用，
业务代码机会全部可以重用，诱惑太大了。

##本地存储
本地存储用了一些非常好的库[react-native-storage](https://github.com/sunnylqm/react-native-storage),支持JS对象的存储和读取，还支持从服务器端自动fetch功能，
不过我没有使用。

##动画
动画API用起来不是特别容易，简单用了一下实现了评论按钮很据用户拖动评论按钮做出显示和隐藏的动画。后来发现了一个
非常棒的库[react-native-animatable](https://github.com/oblador/react-native-animatable)，登录失败的后的错误提示用了他的动画效果，非常简单，代码可读性很高，非常感谢。

##三方登录
三方登录在国内是App必备，主要集成了wechat做为第三方登录和分享。在比较了几个实现之后用了qianlong的实现，
他们的文档和API写的很棒，支持订阅wechat回调App的事件监听，这点非常重要和贴心。美中不足的是Android和iOS的实现
分开了，导致我在项目中又写了一层去适配iOS和Android，提过issue，不过qianlong的同学动力不足，但瑕不掩瑜。
我自己因为有分享本地图片需求，提了pr给他们，iOS的同学帮忙merge了，Android同学自己改了下，动了接口，导致我不得
不用自己的fork，还好npm真心强大可以直接引用github地址。

###附上我的分支:

[wechat Android](https://github.com/buhe/react-native-wechat-android.git#449209c)

[wechat iOS](https://github.com/buhe/react-native-wechat-ios.git#2d00cd6)

###国际版Log in with Facebook
国际版是面向Play Store和美国App Store，官方的SDK只支持iOS版本，万能的github网友，提供了一个很棒的实现，
从名字可以看出来只实现了login功能，因为自己的需求，可耻的提交了一个pr。估计不会被合并吧，只好继续用自己的
分支:

[Facebook Login](https://github.com/buhe/react-native-facebook-login.git#7ca889d)

##视频播放组件

视频播放是这个App的主要功能，一个非常棒的React Native项目近乎完美的解决了我的问题。不过还是美中不足，他的Android
版本只能播放在线视频和Asset中的视频，国内一贯的做法是视频缓存到本地SD Card中。所以不得不改了几行代码，改的比较匆忙
估计被merge的机会不大，有空走心的好好改改。

[React-Native-Video](https://github.com/brentvatne/react-native-video)

修改之后的分支:

[React-Native-Video](https:////github.com/buhe/react-native-video.git#d872933)

##图表组件

目前没有人实现，自己写了一个还没整理好开源出来，挖了个坑[React-Native-Chart](https://github.com/buhe/react-native-chart)
原理是桥接了[iosCharts](https://github.com/danielgindi/ios-charts) 和 [MPAndroidCharts](https://github.com/PhilJay/MPAndroidChart)

##[Code push](https://github.com/Microsoft/react-native-code-push)
大微软的代码动态更新技术，准备1.2版本的时候试用一下

##其他在这个过程中写的组件和pr
[react-native-fs-modal](https://github.com/buhe/react-native-fs-modal.git#275c225)

[react-native-progress-bar](https://github.com/buhe/react-native-progress-bar.git#72a7217)

[react-native-countdown](https://github.com/buhe/react-native-countdown)





