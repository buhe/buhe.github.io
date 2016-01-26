---
layout:     post
title:      "HireDash 技术架构"
subtitle:   "There is no such thing as a great talent without great will - power."
date:       2015-09-10 12:00:00
author:     "bu he"
header-img: "img/post-bg-01.jpg"
---

##整体架构
采用Reactjs + Express + Mongodb 的配套，Express 和 Mongodb是经过时间验证的产品,Express 简洁有力，基于拦截器的架构和Http的模型非常契合。Mongodb结构灵活,配合[monogose](https://github.com/Automattic/mongoose)使用，触感丝滑毫无阻力。

##Reactjs
[Reactjs](https://github.com/facebook/react)是最近两年来前端的风猪。由Facebook公司开发并开源,组件化的开发方式让原本不熟悉前端的同学也能快速上手，前端虽然坑深坑广，但也从侧面说明前端发展迅速，工具丰富。在用Reactjs开发过程中使用了[Webpack]()和众多强大的插件,完成整个开发生命周期。下面推荐几个

##[webpack-dev-server]() + [HotModuleReplacementPlugin]()
采用了这两个工具之后,就可以实现所谓的live-reload。实现改变代码,css后不刷新，并能保留React的state，可以提高开发效率和方便调试，实际用过之后非常棒。

##[autoprefixer]()
```
postcss: [ autoprefixer({ browsers: ['last 2 versions'] }) ],
```
这个工具也非常好，是postcss工具链的一部分，可以自动添加浏览器prefix，例如我们使用了flex布局，各大浏览器有私有prefix，用了这个工具之后就省了很多工作量，快试试吧。

##Reactjs 和 [React Native] 的重用
我们同时采用了Reactjs和React Native做双端开发。这样的好处是我们重用了业务层几乎所有代码，UI也有部分重用。