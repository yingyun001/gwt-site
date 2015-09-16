编译一个 GWT 应用程序：介绍
===

在本教程中，您将会学习写一个简单的 AJAX 应用程序 —— 股票查看器。

继续向下看并试用它。添加一些股票代码，看看它是如果工作的。

<iframe name="StockWatcher" src="gettingstarted/StockWatcher.html"
        style="border: none; width: 450px; height: 300px"></iframe>

在编译股票查看器的过程中，您会了解到 GWT 是如何为您提供工具的：

*   在您选择的 Java IDE 中写浏览器应用程序
*   在 GWT 的开发模式中编译 Java
*   交叉编译 Java 代码，使其成为高优化的 JavaScript
*   为多浏览器 (JavaScript) 的实现来维护基于 Java 代码。

### 使用了 GWT 的 AJAX 应用程序开发过程

本教程将一个典型的应用程序开发周期分成了 8 个部分。每一部分都是基于前一个部分进行编译的。在股票查看器这个应用程序的基本视线中，所有的功能都是在客户端进行编码的。服务器端编码和客户端/服务器端的通信是在[其它教程](index.html)中进行讲解的。

| 任务：您要做什么 | 概念：您将要学到什么 | GWT 工具和 APIs: 您将会用到什么 |
| ---------------- |   ------------------ | ------------------------------- |
| 1. [创建一个 GWT 项目](create.html) | 生成您所需要的文件和目录。 | Google Plugin for Eclipse; GWT 命令行工具 webAppCreator; 开发模式 |
| 2. [设计应用程序](design.html) | 确认需求，限制和实现策略 | 语言限制 |
| 3. [编译用户界面](buildui.html) | 为视图进行布局并添加用户界面组件。 | GWT 的界面工具集和面板，Root 面板 |
| 4. [管理客户端的事件](manageevents.html) | 处理鼠标和键盘的事件。 | ClickHandler 接口和 KeyPressHandler 接口 |
| 5. [在客户端上编写功能代码](codeclient.html) | 为多浏览器的实现维护一套代码库。学习使用 Java IDE 的特性，例如重构和代码补全 | 多个 GWT 方法。 |
| 6. [调试 GWT 应用程序](debug.html) | 在将 Java 代码编译成 JavaScript 代码前先调试 Java 代码。通过让你的 Java IDE 在开发模式下运行应用程序来发挥调试工具的作用。 | 开发模式 |
| 7. [应用样式](style.html) | 将视觉风格应用到应用程序中。在 CSS 中定义视觉风格。以编程的方式在 HTML 的元素上设置 class 属性。动态的更改样式。包括静态样式，例如图片文件。 | GWT 模块; GWT 主题; 应用程序样式表; GWT 方法: addStyleName, addStyleDependentName, setStyleName; automatic resource inclusion |
| 8. [编译 GWT 应用程序](compile.html) | 将您的客户端的 Java 代码编译成 JavaScript。在生产模式下进行测试。了解延迟绑定的好处。 | GWT 编译器。 |

## 下一步

请您务必在[开始之前](index.html#prerequisites)设置好 Java SDK 环境变量，安装好 Java IDE（例如 Eclipse）和最新的 GWT。

您现在应该准备好创建一个 GWT 项目了。

[步骤 1: 创建一个 GWT 项目](create.html)
