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

### 初始应用程序 <a id="starter"></a>

如果您创建了一个新的 GWT 应用程序，默认情况下它会创建像下面这样的比较简单的初始应用程序。该应用程序会在您开发之前帮助您测试所有的组件是否已经安装完毕。当您开始写 StockWatcher 应用程序的时候，将初始应用程序的代码替换为您自己的代码就可以了。

![img](images/CreateStarterApplication.png)


## 检测项目组件 <a id="components"></a>

让我们来检测一些已经生成的文件并看看它是如何整合到一起并最终形成一个 GWT 项目的。

### 模块的 XML 配置文件

打开模块的 XML 配置文件, StockWatcher/src/com/google/gwt/sample/stockwatcher/StockWatcher.gwt.xml。

这个文件里包含了 GWT 模块的定义，组成一个 GWT 应用程序所需资源的集合或者是一个共享的包。默认情况下，StockWatcher 继承了每个项目都需要的核心 GWT 功能。或者，您还可以指定其它 GWT 让 StockWatcher 来继承。


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


在模块的 XML 配置文件中，您制定了应用程序的入口类。
为了编译它，一个 GWT 模块必须指定一个入口点。如果一个 GWT 模块中没有入口点的话，那么它只能被其它模块所继承。该配置文件中还可以包含其它模块，前提条件是在这些模块的 XML 配置文件中也同样指定了入口点。如果是这样的话，您的模块中就回有多个入口点。每个入口点依次执行。

默认情况下，StockWatcher 使用两个样式表：模式的 GWT 样式表 standard.css（这个 CSS 是通过继承主题而被引用的）和应用程序样式表 StockWatcher.css（该 CSS 是由 webAppCreator 生成的）。您会在本教程的之后的部分中学到如何重写默认 GWT 样式。

### 首页面

打开首页面,即 StockWatcher/war/StockWatcher.html。

web 应用程序在 HTML 文档中执行。在 GWT 中，我们调用这个首页面。例如，StockWatcher 项目的首页面就是 StockWatcher.html。

首页面引用了应用程序的样式表，即 StockWatcher.css。

主页面引用了 JavaScript (主要负责页面上动态元素的）源代码的路径（由 GWT 生成的）。整个 body 元素的内容都会被动态的生成，例如，初始应用程序就是这样做的。但是，当您实现 StockWatcher 应用程序的时候，那么静态元素和动态元素会您都会用到。您需要创建一个 `<div>` 元素，它的作用是为页面动态生成的部分提高预留空位的。

#### 选择 Quirks 模式还是标准模式

为了更好的实现跨浏览器兼容，GWT 为 HTML 4.01 过度版提供了文档类型声明。反过来，它又为 “Quirks 模式”设置了浏览器渲染引擎。如果您想将应用程序渲染成“标准模式”。这有[很多其它文档类型](http://hsivonen.iki.fi/doctype/) 您可以使用它来强制使浏览器渲染成这个模式。一般来讲，GWT 应用程序在“标准模式”下工作能像在 “Quirks 模式”下工作一样就好了，但是在某些情况下使用像面板这类的界面工具集会有一些渲染上的瑕疵。这个问题已经在 GWT 1.5 以及以后的版本中做了优化，不过还需要做更多的努力才能将这种问题彻底解决掉。

#### 保存浏览器的历史记录

GWT 提供了一种机制可以让您的应用程序更对用户的胃口，特别是在一些场景下浏览器是否可以点击回退按扭以作为多页面向导或是一个购物车/结帐的场景下的一个必要功能。主页面包含了 iframe 标签，它为您的 GWT 应用程序整合了历史记录的功能。

为了学习更多关于管理 GWT 应用程序的浏览器历史记录内容，请见开发者文档：[历史记录](../DevGuideCodingBasics.html#DevGuideHistory)。


### 应用程序的样式表

打开应用程序的样式表，即 StockWatcher/war/StockWatcher.css 这个文件。

每个项目都或多或少会和样式表有关系。默认情况下，该应用程序的样式表，即 StockWatcher.css 包含了初始应用程序的样式规则。在本教程的[应用样式](style.html) 部分，您可以将初始应用的样式规则替换为 StockWatcher 应用程序的样式规则。

正像任何一个 web 页面，您可以指定多个样式表。以继承顺序列出所有多个样式表。换言之，样式表最后列出的就是最具体的样式规则了。

### Java 源代码

打开 StockWatcher 入口类的源代码文件，即 StockWatcher/src/com/google/gwt/sample/stockwatcher/client/StockWatcher.java。

现在 StockWatcher.java 中包含了初始程序的 Java 源码。在本教程中，您可以将这些代码替换为 StockWatcher 项目的客户端代码。

StockWatcher 类实现了 GWT 接口 [EntryPoint](/javadoc/latest/com/google/gwt/core/client/EntryPoint.html)。该接口中定义了 onModuleLoad 方法。因为 StockWatcher 类被指定为了 StockWatcher 模块定义的入口类，所以当您开启 StockWatcher 项目时，onModuleLoad 就会被调用。

StockWatcher 类通过其它的 GWT 模块（那些被您加至 StockWatcher 模块定义，即 StockWatcher.gwt.xml 中的模块）来继承方法。例如，当您编译用户界面时，您就可以从 com.google.gwt.user.client.ui 包中获取类型和资源，因为它是 GWT 模块 com.google.gwt.user.User 中的 GWT 核心功能。

## 下面做什么

现在您已经为股票查看器这个应用程序创建了桩文件并将其加载到 Eclipse（或者您使用的其它 Java IDE）中。

现在您要准备设置 StockWatcher 应用程序了。

[Step 2: 设计应用程序](design.html)
