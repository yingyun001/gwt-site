创建
===

您应该已经下载了最新的 GWT 版本。

在这一部分，您将会使用 Google Plugin for Eclipse 或者 GWT 命令行工具（webAppCreator）来创建股票查看器项目。这些工具能够生成您所需要的项目子目录以及文件。为了测试您的项目是否配置正确，您还要以开发模式来运行 GWT 初始应用程序。然后您可以检测创建出来的项目文件。

1.  [创建一个 GWT 应用程序。](#create)
2.  [测试默认的项目组件。](#test)
3.  [检测项目组件。](#components)

##  创建 GWT 应用程序 <a id="create"></a>

### 使用 Eclipse 来创建股票查看器应用程序。

使用 GWT 的好处之一就是您可以使用 Java IDE 提供的工具（例如重构，代码补全和调试）。在本教程中，我们将会使用 Eclipse，因为它是开源的。不过您也可以使用自己喜爱的 Java IDE。

Google Plugin for Eclipse 包含了创建 GWT 应用程序的向导。下面是创建起始应用程序的步骤。

1.  在工具栏中点击新建网页应用程序按扭 ![icon](images/NewWebApplicationProject.png).
2.  填写项目细节：

    1.  输入项目的名称："StockWatcher"。
    2.  输入包名： "com.google.gwt.sample.stockwatcher"。
    3.  确保 `Use Google Web Toolkit` 单选框已经被勾选且选择了其中的 `Use default SDK (GWT)` 选项。
    4.  （另外）如果您正在使用 Google App Engine 的话，请您确保 `Use Google App Engine` 已经被够勾选且选择了其中的 `Use default SDK (App Engine)` 选项。
    5.  如果您安装了 Google Plugin for Eclipse，却还没有安装 SDK 的话，您应该点击 `Configure SDKs...`，来确定 GWT 被解压的目录。

3.  点击`完成`按扭。

### 在不使用 Eclipse 的情况下创建股票查看器应用程序。

webAppCreator 是一个包含在下载的 GWT 中的命令行工具，它生成了您所需要的项目子目录和文件。它创建了一个起始应用程序，您可以通过运行它来确保所有组件是否已经被创建并正确的挂接到了一起。当您开发您自己的应用程序的时候，您可以将初始代码替换为您的代码。

自 GWT 1.6 开始，先前使用的命令行工具 projectCreator 和 applicationCreator 都被整合到了 webAppCreator 中。

针对 StockWatcher 项目，您运行 webAppCreator 的时候会用到以下参数。

| 参数 | 定义 | 实例 |
| ---- | ---- | ---- |
| -out | 放置生成文件的目录。 | StockWatcher | 
| -junit | 您系统上 junit.jar 的绝对路径名。您可以在 [sourceforge](http://junit.sourceforge.net/) 下载 JUnit，您还可以使用和您的 Eclipse 相匹配的 JUnit。 | <ul><li>(PC) C:\eclipse\plugins\org.junit_3.8.2.v200706111738\junit.jar</li><li>(Mac) /Users/myname/eclipse/plugins/org.junit_3.8.2.v200706111738/junit.jar</li> |
| moduleName | 您想要创建的 GWT 模块的名称。 | com.google.gwt.sample.stockwatcher.StockWatcher |

1.  创建应用程序 —— 股票查看器
    *  在命令行中运行 webAppCreator。
    *  在单独一行中输入命令。（实例为了增加可读性，采取分行显示的方式。）
    *  用您系统中的 junit.jar 的绝对路径来替换下面实例中的 junit.jar 路径名。

    Windows：

        webAppCreator -out StockWatcher
                      -junit "C:\eclipse\plugins\org.junit_3.8.2.v200706111738\junit.jar"
                      com.google.gwt.sample.stockwatcher.StockWatcher

    Linux：

        ./webAppCreator -out StockWatcher
                        -junit "C:\eclipse\plugins\org.junit_3.8.2.v200706111738\junit.jar"
                        com.google.gwt.sample.stockwatcher.StockWatcher

    **注意：** _-junit_ 参数是可选的。如果您的系统中没有安装 junit 或者您不想在该应用程序中使用 junit，您可以不添加这个 junit 选项。

    **提示：** 如果您在环境变量中添加了 GWT 命令行，您就不必写绝对路径了。

2.  GWT webAppCreator 生成了您所需的项目子目录和文件。

```
Created directory StockWatcher/src
Created directory StockWatcher/war
Created directory StockWatcher/war/WEB-INF
Created directory StockWatcher/war/WEB-INF/lib
Created directory StockWatcher/src/com/google/gwt/sample/stockwatcher
Created directory StockWatcher/src/com/google/gwt/sample/stockwatcher/client
Created directory StockWatcher/src/com/google/gwt/sample/stockwatcher/server
Created directory StockWatcher/test/com/google/gwt/sample/stockwatcher/client
Created file StockWatcher/src/com/google/gwt/sample/stockwatcher/StockWatcher.gwt.xml
Created file StockWatcher/war/StockWatcher.html
Created file StockWatcher/war/StockWatcher.css
Created file StockWatcher/war/WEB-INF/web.xml
Created file StockWatcher/src/com/google/gwt/sample/stockwatcher/client/StockWatcher.java
Created file StockWatcher/src/com/google/gwt/sample/stockwatcher/client/GreetingService.java
Created file StockWatcher/src/com/google/gwt/sample/stockwatcher/client/GreetingServiceAsync.java
Created file StockWatcher/src/com/google/gwt/sample/stockwatcher/server/GreetingServiceImpl.java
Created file StockWatcher/build.xml
Created file StockWatcher/README.txt
Created file StockWatcher/test/com/google/gwt/sample/stockwatcher/client/StockWatcherTest.java
Created file StockWatcher/.project
Created file StockWatcher/.classpath
Created file StockWatcher/StockWatcher.launch
Created file StockWatcher/StockWatcherTest-dev.launch
Created file StockWatcher/StockWatcherTest-prod.launch
Created file StockWatcher/war/WEB-INF/lib/gwt-servlet.jar

```

### 创建的目录

*   /src/com/google/gwt/sample/stockwatcher
包含了 GWT 的模块定义并初始化应用程序文件。
*   /test/com/google/gwt/sample/stockwatcher
包含了 Junit 测试目录和初始测试类。
*   /war
包含了公共的静态资源，例如图片文件，样式表和 HTML 主页。
*   /war/WEB-INF
包含了 Java web 应用程序文件。
*   /war/WEB-INF/lib
包含了 Java web 应用程序二进制文件。

从 GWT 1.6 开始，静态文件都移到了 /war 目录下。

### 创建的文件

*   StockWatcher.gwt.xml
GWT 模块定义
*   StockWatcher.html
主页面
*   StockWatcher.css
应用程序样式表
*   web.xml
Java web 应用程序描述文件
*   StockWatcher.java
GWT 入口类
*   GreetingService.java, GreetingServiceAsync.java, GreetingServiceImpl.java
GWT 简单的 RPC 类
*   gwt-servlet.jar
GWT 服务器运行时库
*   StockWatcherTest.java
StockWatcher 的初始测试用例

### 创建的脚本

*   build.xml
Ant 构建了开发模式下用于运行应用程序的文件或是命令行中调用 GWT 编译器的文件。

### 创建的 Eclipse 文件

*   .project
*   .classpath
*   StockWatcher.launch
*   StockWatcherTest-dev.launch
*   StockWatcherTest-prod.launch

想要看到 webAppCreator 的全部选项，请见：命令行工具，[webAppCreator](../RefCommandLineTools.html#webAppCreator)。

想要了解更多关于项目结构的信息，请见：开发者指南 [目录/包 惯例](../DevGuideOrganizingProjects.html#DevGuideDirectoriesPackageConventions).

##  测试默认项目组件 <a id="test"></a>

想要查看创建的所有项目组件，需要在开发模式下运行初始应用程序。在开发模式中，您可以在浏览器中和应用程序就行交互，就像程序部署好后你所要做的一样。

### 在 Eclipse 中运行开发模式代码服务器

1.  在包浏览视图中，选择 StockWatcher 项目。
2.  在工具栏中，点击运行按扭（Run as Web Application）。
3.  当开发模式标签打开时，右键点击 URL 进行复制。

    ![img](images/DevModeTab.png)

4.  将 URL 粘贴至浏览器中。

### 在命令行中运行开发模式代码服务器

webAppCreator 创建了一个 ant build 文件，其中 target 的内容是在开发模式下运行应用程序。

1.  在命令行中切换到 StockWatcher 目录
2.  执行：

```
ant devmode
```

**提示：** 如果您在环境变量中添加了 Ant 命令行工具，您就不必写它的绝对路径了。

在开发模式下会有两个标签：开发模式代码服务器和 Jetty HTTP 服务器。点击“启动默认浏览器”按扭，您就可以使用您默认的浏览器启动开发模式下的 StockWatcher。或者，您也可以点击“复制到剪贴板”，并将其粘贴到您的浏览器中。

![img](images/DevModeNoEclipse.png)

### 连接到开发模式代码服务器

一旦您开启了开发模式（不管是在 Eclipse 中还是在 build.xml 的脚本中）并在浏览器中进入了 URL，浏览器会尝试去连接代码服务器。如果这是您第一次在开发模式下运行一个 GWT 应用程序，您需要在浏览器中安装 Toolkit Developer 插件。跟随本教程来安装该插件，然后重启浏览器，再进入到刚才的 URL 中。

![img](images/MissingPlugin.png)

### rter Application <a id="starter"></a>

When you create a new web application with GWT, by default it creates a simple, starter application as shown below.  This application helps you test that all the components are installed and configured before you start development. When you start writing the StockWatcher application, you'll replace this starter application code with your own.

![img](images/CreateStarterApplication.png)


##  Examining the project components <a id="components"></a>

Let's examine some of the generated files and see how they fit together to form your GWT project.

### The module XML file

Open the module XML file, StockWatcher/src/com/google/gwt/sample/stockwatcher/StockWatcher.gwt.xml.

It contains the definition of the GWT module, the collection of resources that comprise a GWT application or a shared package. By default, StockWatcher inherits the core GWT functionality required for every project. Optionally, you can specify other GWT modules to inherit from.

```
<?xml version="1.0" encoding="UTF-8"?>
<module rename-to='stockwatcher'>
  <!-- Inherit the core Web Toolkit stuff.                        -->
  <inherits name='com.google.gwt.user.User'/>

  <!-- Inherit the default GWT style sheet.  You can change       -->
  <!-- the theme of your GWT application by uncommenting          -->
  <!-- any one of the following lines.                            -->
  <inherits name='com.google.gwt.user.theme.standard.Standard'/>
  <!-- <inherits name="com.google.gwt.user.theme.chrome.Chrome"/> -->
  <!-- <inherits name="com.google.gwt.user.theme.dark.Dark"/>     -->

  <!-- Other module inherits                                      -->

  <!-- Specify the app entry point class.                         -->
  <entry-point class='com.google.gwt.sample.stockwatcher.client.StockWatcher'/>

  <!-- Specify the paths for translatable code                    -->
  <source path='client'/>

</module>
```

In the module XML file, you specify your application's entry point class.
In order to compile, a GWT module must specify an entry point. If a GWT module has no entry point, then it can only be inherited by other modules.
It is possible to include other modules that have entry points specified in their module XML files. If so, then your module would have multiple entry points. Each entry point is executed in sequence.

By default, StockWatcher uses two style sheets: the default GWT style sheet, standard.css (which is referenced via the inherited theme), and the application style sheet, StockWatcher.css which was generated by webAppCreator. Later in this tutorial, you'll learn how to override the default GWT styles.

### The Host Page

Open the host page, StockWatcher/war/StockWatcher.html.

The code for a web application executes within an HTML document. In GWT, we call this the host page. For example, the host page for the StockWatcher project is StockWatcher.html.

The host page references the application style sheet, StockWatcher.css.

The host page references the path of JavaScript source code (generated by GWT) responsible for the dynamic elements on the page. The contents of the entire body element can be generated dynamically, for example, as it is with starter application. However, when you implement the StockWatcher application, you will use a mix of static and dynamic elements. You'll create an HTML `<div>` element to use as placeholder for the dynamically generated portions of the page.

#### Selecting Quirks Mode vs. Standards Mode

To provide better cross-browser compatibility, GWT sets the doctype declaration to HTML 4.01 Transitional. This, in turn, sets the browser's rendering engine to "Quirks Mode". If you instead want to render the application in "Standards Mode", there are a [number of other doctypes](http://hsivonen.iki.fi/doctype/) you can use to force the browser to this render mode. In general, GWT applications will work in "Standards Mode" just as well as "Quirks Mode", but in some cases using widgets like panels and such may not render correctly. This problem has been greatly improved since GWT 1.5, and more work is being done to solve this problem once and for all.

#### Preserving Browser History

GWT provides a mechanism for helping your application meet users' expectations of a web page, specifically in their ability to use the browser's back button in such situations as a multi-page wizard or a shopping cart/checkout scenario. The host page contains the iframe tag necessary for incorporating history support in your GWT application.

To learn more about managing browser history in a GWT application, see the Developer's Guide, [History](../DevGuideCodingBasics.html#DevGuideHistory).

### The Application Style Sheet

Open the application style sheet, StockWatcher/war/StockWatcher.css.

A style sheet is associated with each project. By default, the application style sheet, StockWatcher.css, contains style rules for the starter application. In the [Applying Style](style.html) section of this tutorial, you'll replace the style rules for the starter application, with the style rules for the StockWatcher application.

Just as for any web page, you can specify multiple style sheets. List multiple style sheets in their order of inheritance; that is, with the most specific style rules in the last style sheet listed.

### The Java source code

Open the source for the StockWatcher entry point class, StockWatcher/src/com/google/gwt/sample/stockwatcher/client/StockWatcher.java.

Currently, StockWatcher.java contains the Java source for the starter application. In this tutorial, you'll replace this code with the client-side code for StockWatcher.

The StockWatcher class implements the GWT interface [EntryPoint](/javadoc/latest/com/google/gwt/core/client/EntryPoint.html). It contains the method onModuleLoad. Because the StockWatcher class is specified as the entry point class in StockWatcher's module definition, when you launch StockWatcher the onModuleLoad method is called.

The StockWatcher class inherits functionality via other GWT modules you included in StockWatcher's module definition (StockWatcher.gwt.xml). For example, when building the user interface, you'll be able to include types and resources from the package com.google.gwt.user.client.ui because it is part of the GWT core functionality included in the GWT module com.google.gwt.user.User.

## What's Next

At this point you've created the stub files for the StockWatcher application and loaded the project into Eclipse (or whatever Java IDE you prefer).

Now you're ready to design the StockWatcher application.

[Step 2: Designing the Application](design.html)
