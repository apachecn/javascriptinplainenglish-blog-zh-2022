# 什么是服务器？—对初级开发人员的解释

> 原文：<https://javascript.plainenglish.io/what-is-a-server-explanation-for-young-developers-2511d8b313b7?source=collection_archive---------9----------------------->

## 第 1 部分:更深入地了解 web 应用程序周围的生态系统，以便成为一名更自信的程序员。

![](img/802a9b0fe454e6f51a3abbb070039257.png)

这是一个迷你系列，旨在加深对 web 应用生态系统的理解，以便成为一个更自信的程序员。

第 1 部分:什么是服务器？

[第二部分:云计算&容器](https://medium.com/@designbygio/virtualization-containers-an-explanation-for-beginner-developers-2f0257122172)

第 3 部分:托管解决方案(即将推出)

服务器是一个众所周知的术语，根据上下文有许多不同的含义。
这个词经常在没有进一步解释的情况下使用，如果你对计算机/编程世界相对陌生，它会导致混乱和不安全感。

# 真正的服务器是什么意思？

我的确读过*服务器*的定义一百万遍，但我还是花了很长时间才明白什么是服务器。在向我的学生解释它的时候，我意识到为什么一开始会如此困惑。
根据上下文，服务器这个术语可能有多种含义。这就是为什么服务器的官方定义非常抽象，因此难以理解。
来自维基百科:

*在* [*计算*](https://en.wikipedia.org/wiki/Computing) *中，一台* ***服务器***[*计算机*](https://en.wikipedia.org/wiki/Computer) *硬件或软件(* [*计算机程序*](https://en.wikipedia.org/wiki/Computer_program) *)为其他程序或设备提供功能，称为* [*客户端*](https://en.wikipedia.org/wiki/Client_(computing))

我是这样重新解读这个定义的:
服务器是计算机或软件的物理部分(所以是我可以安装在我的计算机上的东西)。有了服务器，我可以为其他设备提供“要发生的事情”或“要做的事情”。

我的第一个想法是:服务器是我的个人电脑的一部分(因为是硬件部分),或者它可以安装在上面，就像我安装任何其他软件一样，如 Discord 或 Visual Studio 代码。
但是，如果我想到一台*服务器*我脑海中的第一个图像是这个房间里排满了黑匣子...就像我在一些数据中心广告中看到的那样。
那么哪个思想是正确的呢？两个都是！

![](img/c0a386427daaba1555c33c2a1bc64f89.png)

Servers in a data center

术语*服务器*可以指:

*   **物理机器**(我们在数据中心广告或黑客相关电影中看到的那些黑匣子)
*   **虚拟机**(我们将在后面看到细节——现在考虑一台在当前操作系统之上托管全新操作系统的计算机)
*   **我们安装在电脑上的一个软件**。

所有这些东西有什么共同点？目的。
一台服务器向另一台计算机提供功能。
这是什么意思？
这意味着有另一个设备(电脑、手机、树莓、智能电视……)要求服务器执行一些操作，例如从数据库中抓取数据、返回网页、发送电子邮件、存储和管理文件。这些操作通常被称为**服务**。
向服务器请求或从服务器接收这些操作的其他设备或机器通常被称为:**客户端**。
服务器和客户端之间的这种服务交换称为:客户端-服务器模型。

# 服务器与客户端

我觉得在这种情况下澄清这两个术语的定义是很重要的。
特别是如果你来自设计、前端或训练营，当使用术语**客户**时，你可能会感到困惑。
你可能已经了解到*客户端*是你的应用的前端代码，后端是后端代码。在应用程序代码的上下文中，这是正确的。

当你编写自己的应用程序时，你会有一些 HTML、CSS 和 JavaScript 文件，这些文件是你的前端代码，还有一些其他的文件是你选择的后端语言(PHP、Python、Java、Rust 等)。)来表示您的后端代码。
在*服务器*的上下文中，当我们谈论*客户端*时，我们不是指应用程序的前端代码，而是指整个应用程序。
**客户端**是任何机器(电脑、电话、树莓派等。)与服务器通信。

让我们举一个例子来说明:

*   我有一份网上订餐的申请。
*   这个应用程序是用 React 和 Node.js 编写的。
*   它使用 API 来检索餐馆列表并显示给用户。
*   我在 Heroku 上托管这个应用程序。在这方面，Heroku 是我们的服务器。
*   订餐应用程序是客户端。
*   React 是前端代码的客户端框架。
*   Node.js 是后端代码的“框架”。( [Nodejs 并不是一个真正的框架](https://www.effectussoftware.com/blog/node-js-a-framework/)，但为了简洁起见，我在这里这样称呼它)。
*   为应用程序从数据库中检索餐馆列表是一项服务。

# 不同类型的服务器

了解服务器至少需要两个组件是很重要的:操作系统和软件。操作系统需要访问运行服务器所需的硬件部件。
需要该软件来实现服务器的任何目的:即向客户端提供 HTML 页面、接收和发送电子邮件、托管数据库、管理各种打印请求以及与打印机通信。
在我看来，有两个相关的部门来理解不同类型的服务器。

## 硬件或软硬件类别:

第一个与硬件或如何访问物理机器资源更相关。我们已经讨论过了，但是让我们再详细讨论一下。

**物理服务器:**
物理服务器基本上就是一台用来运行专门做服务器的软件的计算机。如果我们安装一个服务器软件，比如 Apache、NGINX、MAMP/XAMP 等，我们的个人电脑就可以成为一个服务器。但是在大多数情况下，当使用术语物理服务器时，它指的是单独充当服务器的机器。

为了最大限度地优化服务器能力，最好不要与其他软件共享计算机资源，这样所有的计算机 CPU、内存等将只用于处理与服务器相关的任务。
这就是为什么一台计算机经常被用作服务器，并且它只包含一个服务器软件(或者几乎只包含一个服务器软件)。
如今，物理服务器可以是一个小盒子。

**虚拟机:**
虚拟服务器是一种允许虚拟计算机存在于另一台物理计算机上软件。基本上，在一台物理计算机上，我们可以安装一个允许我们安装操作系统的软件。该软件将负责与操作系统进行通信，在那里可以找到 CPU、内存等硬件资源。
一台物理机上可以安装多种虚拟服务器。通过这种方式，我们节省了空间和金钱，为各种服务器共享 CPU、内存或 RAM 等资源。每个虚拟服务器都有自己的操作系统、用户和应用程序。那部分是私人的。
基本上和你在自己的笔记本电脑上安装 Windows、Linux、macOS 是一样的。
它们都将使用相同的 CPU、RAM 等，但每次安装都需要不同的用户名和密码来访问，如果您在 Windows 中保存了一个文件，则在 Linux 安装中将无法访问该文件。如果你想更多地了解虚拟机是如何工作的，请继续阅读本系列的下一篇文章。

## 作为软件的服务器

在这种情况下，服务器只是一个安装在机器上的软件。
服务器的不同用途将导致选择一个专门为此目的而创建的特定软件。
一些最常见的服务器软件有:

*   网络服务器软件
*   邮件服务器软件
*   数据库服务器软件
*   文件服务器软件

如果你想看完整的名单，你可以在这里查看[。](https://www.networkstraining.com/different-types-of-servers/)

## 简单的总结

如果我们简化所有这些信息，服务器就是我们用来配置计算机的软件。
它可以是仅用于此目的的计算机，可以是托管各种操作系统和用户的计算机，可以是充当普通个人计算机并在其中安装了服务器软件的计算机。这种方式很难定义什么是服务器，也很令人困惑。

# CRA 和 Visual Studio 代码

令人惊讶的是，有一些工具可以让开发人员只关注代码，而不关心其他任何事情，但是理解“魔力”来自哪里也很重要。

如果您习惯于使用 CRA 或 Visual Studio Code Live Share 开发您的应用程序，您可能已经运行了一些命令或单击了一些按钮，并且仅仅能够看到您的应用程序在`https://localhost:3000`或`https://localhost:5500`或类似的端口上运行。这是可能的，因为 CRA 在幕后使用了 web 服务器，Visual Studio 代码实时共享扩展也是如此。
该服务器获取您的代码，连接到本地服务器(localhost)和特定端口，并在那里显示 index.html。没有服务器，你的应用程序将无法显示在`localhost:3000`或者你使用的任何其他端口下。

给你。感谢您的阅读。

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*[***YouTube***](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)*[***不和***](https://discord.gg/GtDtUAvyhW) *。对增长黑客感兴趣？检查* [***电路***](https://circuit.ooo/) *。***