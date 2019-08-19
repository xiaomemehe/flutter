

# 入门
## 移动开发技术简介
1. 原生开发
2. 
跨平台开发
>* H5+原生（Cordova、Ionic、微信小程序）
>* JavaScript开发+原生渲染 （React Native、Weex、快应用）
>* 自绘UI+原生(QT for mobile、Flutter)

## DOM树与控件树
  简单来说，DOM就是文档树，与用户界面控件树对应，在前端开发中通常指HTML对应的渲染树，但广义的DOM也可以指Android中的XML布局文件对应的控件树，而术语DOM操作就是指直接来操作渲染树（或控件树）， 因此，可以看到其实DOM树和控件树是等价的概念，只不过前者常用于Web开发中，而后者常用于原生开发中。
## 响应式编程
  React中提出一个重要思想：***状态改变则UI随之自动改变***，而React框架本身就是响应用户状态改变的事件而执行重新构建用户界面的工作，这就是典型的响应式编程范式

# Flutter简介
Flutter 是 Google推出并开源的移动应用开发框架，主打跨平台、高保真、高性能。开发者可以通过 Dart语言开发 App，一套代码同时运行在 iOS 和 Android平台。 Flutter提供了丰富的组件、接口，开发者可以很快地为 Flutter添加 native扩展。同时 Flutter还使用 Native引擎渲染视图，这无疑能为用户提供良好的体验。
## JIT和AOT
目前，程序主要有两种运行方式：静态编译与动态解释。静态编译的程序在执行前全部被翻译为机器码，通常将这种类型称为AOT （Ahead of time）即 “提前编译”；而解释执行的则是一句一句边翻译边运行，通常将这种类型称为JIT（Just-in-time）即“即时编译”。

![] (https://cdn.jsdelivr.net/gh/flutterchina/flutter-in-action/docs/imgs/1-1.png)
## Flutter Framework
* 这是一个纯 Dart实现的 SDK，它实现了一套基础库，自底向上，我们来简单介绍一下：

* 底下两层（Foundation和Animation、Painting、Gestures）在Google的一些视频中被合并为一个dart UI层，对应的是Flutter中的dart:ui包，它是Flutter引擎暴露的底层UI库，提供动画、手势及绘制能力。

* Rendering层，这一层是一个抽象的布局层，它依赖于dart UI层，Rendering层会构建一个UI树，当UI树有变化时，会计算出有变化的部分，然后更新UI树，最终将UI树绘制到屏幕上，这个过程类似于React中的虚拟DOM。Rendering层可以说是Flutter UI框架最核心的部分，它除了确定每个UI元素的位置、大小之外还要进行坐标变换、绘制(调用底层dart:ui)。

* Widgets层是Flutter提供的的一套基础组件库，在基础组件库之上，Flutter还提供了 Material 和Cupertino两种视觉风格的组件库。而我们Flutter开发的大多数场景，只是和这两层打交道。

## Flutter Engine
* 这是一个纯 C++实现的 SDK，其中包括了 Skia引擎、Dart运行时、文字排版引擎等。在代码调用 dart:ui库时，调用最终会走到Engine层，然后实现真正的绘制逻辑。
