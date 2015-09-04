概述
===

GWT 是一个用于构建并优化复杂的基于浏览器应用程序的开发工具包。它的初衷开发者无需精通浏览器的怪异模式，XMLHttpRequest 和 JavaScript 就可以高效率的开发 web 应用程序。Google 中的许多产品，包括 AdWords（广告关键字），AdSense（广告联盟），Flights（航班搜索服务），Hotel Finder（酒店达人），Offers（团购），Wallet（电子钱包），Blogger（博客）都使用了 GWT。并且 GWT 是开源的，完全免费的，并受到了全世界成千上万开发者拥护。

[在 GWT 2.7.0 中有什么新功能？](release-notes.html#Release_Notes_2_7_0)

## 工具包中都有什么呢？

### SDK

[GWT SDK](learnmore-sdk.html) 包含了 Java 的 API 库，编译器和开发服务器。它允许您用 Java 写客户端的应用程序并将其部署为 JavaScript。

*   [开始](gettingstarted.html)
*   [教程](doc/latest/tutorial/index.html)
*   [开发手册](doc/latest/DevGuide.html)

### Eclipse 的插件

[Eclipse 插件](https://developers.google.com/eclipse/index) 提供了对 GWT 和 App Engine web 项目的 IDE 支持。

*   [开始](usingeclipse.html)

## 用 GWT 开发

### <i class="icon_write"></i> 写代码

GWT SDK 提供了一组核心 Java API 和界面工具集。利用 SDK 您就可以用 Java 语言写 AJAX 应用程序并会将源代码编译成高度优化过的可运行在各种浏览器（包括 Android 系统和 iPhone 系统上的移动端浏览器）中的 JavaScript。
The GWT SDK provides a set of core Java APIs and Widgets. These allow you to write AJAX applications in Java and then compile the source to highly optimized JavaScript that runs across all browsers, including mobile browsers for Android and the iPhone.

Constructing AJAX applications in this manner is more productive thanks to a higher level of abstraction on top of common concepts like DOM manipulation and XHR communication.

You aren't limited to pre-canned widgets either. Anything you can do with the browser's DOM and JavaScript can be done in GWT, including interacting with hand-written JavaScript.

### <i class="icon_debug"></i> Debug

You can debug AJAX applications in your favorite IDE just like you would a desktop application, and in your favorite browser just like you would if you were coding JavaScript. The GWT developer plugin spans the gap between Java bytecode in the  debugger and the browser's JavaScript.

Thanks to the GWT developer plugin, there's no compiling of code to JavaScript to view it in the browser. You can use the same edit-refresh-view cycle you're used to with JavaScript, while at the same time inspect variables, set breakpoints, and utilize all the other debugger tools available to you with Java. And because GWT's development mode is now in the browser itself, you can use tools like Firebug and Inspector as you code in Java.

### <i class="icon_optimise"></i> Optimize

GWT contains two powerful tools for creating optimized web applications. The GWT compiler performs comprehensive optimizations across your codebase &mdash; in-lining methods, removing dead code, optimizing strings, and more. By setting split-points in the code, it can also segment your download into multiple JavaScript fragments, splitting up large applications for faster startup time.

Performance bottlenecks aren't limited to JavaScript. Browser layout and CSS often behave in strange ways that are hard to diagnose. Speed Tracer is a new Chrome Extension in GWT that enables you to diagnose performance problems in the browser.

### <i class="icon_run"></i> Run

When you're ready to deploy, GWT compiles your Java source code into optimized, stand-alone JavaScript files that automatically run on all major browsers, as well as mobile browsers for Android and the iPhone.

## Ready to get started?

[Download the SDK](gettingstarted.html) and get a simple web application up and running. From there, work through the fundamentals of GWT development with the in-depth [tutorials](doc/latest/tutorial/index.html).
