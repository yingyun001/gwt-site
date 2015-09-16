教程：概览
===

该教程致力于那些想要使用 Google 网页工具包来写富 AJAX 应用程序的开发人员。您可能正是一名想将面向对象编程这种软件开发的规则应用到 web 应用程序中并还想利用 Java IDE 工具来开发 web 应用程序的程序员。或许您是一个对 GWT 能够生成高度优化的 JavaScript 这个事实有所怀疑的 JavaScript 小能手们。

即使您不会 HTML, CSS 和 Java，也不会影响您学习本教程。

本教程基于两个例子应用程序的开发，这样用户就可以在每一步学到 GWT 的概念。

* **StockWatcher** 是一个用于监控股市波动的应用程序，您可以从 [github](https://github.com/manolo/gwt-stockwatcher) 中获取源代码。
* **TodoList** 是一个用于创建并维护浏览器中的待办事项清单的应用程序，您可以从 [github](https://github.com/manolo/gwt-polymer-todo-list) 获取代码。

## 在您开始之前 <a id="prerequisites"></a>

在您开始学习本教程之前，我们假设您已经完成了以下这些工作。

1.   安装 Java SDK。
    *  如果您没有安装最新的 Java SDK，请您下载并安装 [Sun Java Standard Edition SDK](http://java.sun.com/javase/downloads/index.jsp)。
2.   安装 Eclipse 或者您喜欢的 Java IDE。
    *  在本教程中我们使用 [Eclipse](http://www.eclipse.org/)，因为它是开源的。但是 GWT 并没有局限在 Eclipse 中。您还可以使用 [IntelliJ](http://www.jetbrains.com/idea/), [NetBeans](http://www.netbeans.org/) 或者其它的您更喜欢的 Java IDE。如果您没有选择 Eclipse 作为您的 Java IDE 的话，那会和本教程中的截屏和一些特定指令些须出入。
    *  如果您的 Java IDE 不包含 Apache Ant 支持的话，请您下载并解压 [Ant](http://ant.apache.org) 进行编译并运行，然后就可以运行 GWT 的应用程序了。
3.   为 Eclipse 安装 Google 插件。
    *  为创建并开发 GWT 应用程序，[Google Plugin for Eclipse](https://developers.google.com/appengine/docs/java/tools/eclipse) 为 Eclipse 添加了一些功能。
4.   下载 Google 网页工具
    *  Google 网页工具可以随着 Google Plugin for Eclipse 一起被下载下来。或者您还可以为您的操作系统下载最新版本的 [Google Web Toolkit](../../../download.html)。
5.   将 GWT 解压到您指定的目录中。
    *  GWT 没有需要安装的项目。所有您需要运行并使用的文件都在解压后的目录中。

您可能还需要进行如下这些操作：

1.   安装 Google App Engine SDK。
    *  Google App Engine 允许您在 Google 架构上运行 Java web 应用程序，包括 GWT 应用程序。App Engine SDK 会随着 Google Plugin for Eclipse 一起被下载下来。或者，您也可以为 Java 另外下载 [App Engine SDK](https://developers.google.com/appengine/downloads)。

2.   [创建并运行您的第一个 web 应用程序](../../../gettingstarted.html#create) - 几个简单的步骤就可以让您熟悉命令行命令。

## GWT 教程 <a id="gwt_tutorials"></a>

### 构建一个简单的 GWT 应用

1.   [构建一个简单的 GWT 应用](gettingstarted.html)
   * 通过开发股票监测系统(stockWatcher)这个应用程序开启我们的 Google Web Toolkit 学习之路。在这里你会学习创建一个 GWT 项目，利用 GWT 的各种小工具(wigdets)和面板(panels)来构建用户界面，用 Java 语言编写客户端功能，在开发模式下 debug，应用 CSS 样式，将 Java 编译成 JavaScript，最后就是学习在生产模式下运行程序了。

### Client-Server 通信

1.   通过 [GWT RPC](RPC.html) 与服务器端进行通信
    *  使用 GWT RPC 添加一个对服务器端的调用。在这里你将会学到异步调用，序列化 Java 对象，并处理异常。
2.   [通过 HTTP 检索 JSON 数据](JSON.html)
    *  通过发送 HTTP 请求从服务器端检索 JSON 数据。同样，我们还可以根据这个方法检索 XML 数据。
3.   [跨站点请求](Xsite.html)
    *  在 SOP 限制的基础上，调用一个远程的服务。

### 国际化

1.   [国际化一个 GWT 应用程序](i18n.html)
    *  利用静态的字符串国际化将 GWT 的用户界面翻译成另外一种语言。

### JUnit 测试

1.   [利用 JUnit 进行单元测试](JUnit.html)
    *  利用 JUnit 为 GWT 应用程序添加单元测试。

### 部署到 Google App Engine 中

1.   [将应用程序部署到 Google App Engine 中](appengine.html)
    *  将 GWT 应用程序部署到 [App Engine](https://developers.google.com/appengine) 中。

### Building Modern Apps with GWT & Polymer

Write responsive GWT applications for mobile and desktop using [Polymer Elements](https://elements.polymer-project.org/) and JsInterop.

   1. [Create](../polymer-tutorial/create.html) a GWT app.
      * Get started wit GWT creating new maven projects from scratch, running and debugging them in SuperDevMode, and including external dependencies.
   2. Design the UI
      * Learn how to use classic [Widgets](../polymer-tutorial/widgets-buildui.html) in UiBinder to build your UI
      * Or learn how to use [Elements](../polymer-tutorial/elements-buildui.html) in UiBinder which is the tendency in modern GWT apps.
   3. Code the application logic
      * Adding event handlers to [Widgets](../polymer-tutorial/widgets-applogic.html) using `@UiHandler` annotations.
      * Or listening to DOM events in [Elements](../polymer-tutorial/elements-applogic.html) based UIs.

