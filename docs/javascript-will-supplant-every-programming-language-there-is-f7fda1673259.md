# JavaScript 将取代现有的所有编程语言

> 原文：<https://javascript.plainenglish.io/javascript-will-supplant-every-programming-language-there-is-f7fda1673259?source=collection_archive---------4----------------------->

## JavaScript——一枚戒指统治一切！

![](img/773fe59f592cb23611eaa960cfe23edb.png)

Image by GoodArtPix via DepositPhotos

过去 40 年的计算机编程教会了你一些关于技术的事情；尤其是技术是如何进来的，并最终被更新更好的东西所取代。具体来说，对于编程语言，我已经看到语言随着流行度、有用性和适应性的变化而变化。

然而，在这个不断变化的语言环境中，没有什么比 JavaScript 更持久、更灵活、更具适应性。

“JavaScript”最初于 1995 年引入网景浏览器，实际上是网景公司创造的一个营销术语，作为网景浏览器中新脚本引擎的名称。一年后，微软将在 Internet Explorer 中引入“JScript”——从而引发了未来 20 年世界上所有 web 开发人员的灾难:浏览器大战。

JavaScript 和 JScript 最初不是很兼容。微软对如何使用专有的命令结构有自己的想法，例如，为了使 DOM 动画化，更不用说它低劣的 CSS 过滤器了。天哪，真是语法混乱。

不需要火箭科学家就知道需要为 BOM 和 DOM 脚本设置某种标准。因此，在 1996 年，网景公司向欧洲计算机制造商协会(ECMA)提交了它提出的标准。这将导致一年后 ECMAScript 标准的发布。

但是网景在浏览器大战中惨败，到 21 世纪初，微软的 IE 浏览器已经获得了一些人所说的 95%的市场份额。毫无疑问，JScript 是 web 上占主导地位的脚本语言。

微软最初参与了 ECMAScript 标准的构建，但后来退出了，或多或少地扼杀了 ECMAScript 4。

幸运的是，到了 2000 年代末，微软重返谈判桌，可以说，ECMAScript 5 的最终规范最终在 2009 年敲定。

其余的，正如他们所说，大多是众所周知的近代史。

具有讽刺意味的是，ECMAScript(现在的官方名称)在法律上不能被称为“JavaScript ”,因为这个术语被 Oracle 注册了商标。但是“JavaScript”这个术语已经完全嵌入到计算和技术的结构中，试图使用这个商标可能是不明智的。

# 超越世俗

除非你在过去十年中一直生活在岩石下，否则众所周知，JavaScript 已经超越了浏览器客户端，现在可以在任何可以运行 Node.js(通常也写作 Node.js，或简称 Node)的平台或操作系统上使用。

事实上，Node.js 运行时是 JavaScript 最终取代所有编程语言的原因。随着 NPM(每个人都称之为“节点包管理器”，但这并不真正代表 NPM)现在在注册表中有超过 130 万个可用的包，NPM 现在是地球上最大的代码库。

我知道，我可以听到你们所有人，Ruby，Python 和 Java 人，在你们翻白眼想知道我在抽什么的时候呻吟。你认为没有什么可以取代[在此插入你最喜欢的语言]。

不，你是对的，没有一种语言会被完全取代；我们中的一些人仍然在编写商业 COBOL 代码。但是就受欢迎程度而言，我们今天最喜爱的语言很有可能无法经受住 JavaScript 日益增长的受欢迎程度。

# JavaScript—易于使用

JavaScript 如此灵活的原因不仅仅是因为它是面向对象的，还因为它是松散类型的。当然，这将把类型脚本纯粹主义者送进概念中，但是对于松散类型的编程语言来说有非常有效的理由——速度和灵活性在这个列表中名列前茅。

类型脚本纯粹主义者认为强类型语言更好，更不容易出错。当然，如果你是个蹩脚的程序员。但这并不是强类型语言的最佳论据。强类型语言确实也有缺点。

关键是，JavaScript 可以做到这两点。选择你的毒药。

JavaScript 也是一种解释语言，也就是说，它不需要在运行时编译。(嗯，除非你写的是 TypeScript 或 CoffeeScript，否则它只会编译成普通的 JS，这是你应该写的，但是我离题了...)编写 JS 代码,“解释器”(在这种情况下是 BOM 或 Node.js 运行时)解释并执行代码，而无需将其编译为机器二进制代码。

# 多线程与异步执行

我们中的一些人喜欢认为 JavaScript 是“多线程”的，因为 Node.js 甚至 BOM 可以旋转多个“工人”(子进程)或利用异步代码执行。

但那并不是真正的“多线程”。事实是，JavaScript 是很好的单线程，在解释器运行时有很好的异步代码执行。

是的，很多人意识到 JavaScript 是单线程的，并开始努力开发项目，使 JavaScript 和 Node.js 真正多线程化。但是这样的项目确实没有抓住重点。仅仅因为你能做多线程的事情并不意味着你需要，甚至不应该。

事实是，对于大多数使用 JavaScript 的用例来说，多线程并不是真正必要的。如果您真的需要多线程(您不需要，您只是认为您需要)，有非常简单的方法来模拟这一点，而不需要用另一个包侵入 Node.js 运行时。

或许最大的原因(借口？)我看到有人希望在一个进程线程出错或失败的情况下产生多个线程，他们不想让整个核心执行停止。

多线程化你的应用并不能解决这个问题。事实上，如果有什么东西坏了，只会引起更大的麻烦。

您真正应该做的是编写更好的代码，对可能的“阻塞操作”进行更好的错误处理，不要再浪费时间试图将简单的事件侦听器或工作子进程复杂化。

在幕后，Node.js 使用 [Libuv](https://en.wikipedia.org/wiki/Libuv) 来处理异步事件，并作为网络和文件系统 I/O 操作的抽象层。Node.js 可以处理数万个非阻塞并发连接。Libuv 使用异步管理的线程池来管理这些“线程”(并发连接)。

如果您的线程池变得非常大，底层操作系统很可能会将工作卸载到多个处理器，有效地“多线程化”您的应用程序，而无需您明确地这样做。

# 范围和结束

如果你看看今天的绝大多数程序员，每个人，我的意思是每个人，都知道并使用 JavaScript，尤其是当你使用 web 应用程序时。

你必须知道。

然而，我曾经和一些人一起工作，他们花时间去了解如何为 web 应用程序编写合适的 JavaScript。就好像他们避免使用它，当他们不得不写的时候，你可以看出他们并没有真正体会到它的力量。

JavaScript 中的可变作用域允许我们做一些非常酷的事情，不仅仅是写“插件”或“闭包”(有时像我这样不记得正确术语的人称为“附件”)。

因为 JavaScript 给了我们全局、局部和现在的块作用域变量，我们可以创建“闭包”，即独立的匿名 JavaScript 函数，它做一些事情(比如运行富控件)并且不干扰其他第三方代码。

我知道你认为提到这样的东西很愚蠢，但是对于刚刚学习 JS 的人来说，这些是语言的重要方面，也是 JavaScript 如此有用和灵活的部分原因。

# jQuery——仍然是有史以来最流行的 JavaScript 库

每年，我们都会看到列出“前 10 名”或“前 25 名[在此插入年份]最受欢迎的 JavaScript 框架”的文章以及其他类似的废话。我们能不能别废话了？定义“流行”？

事实是，在商业和企业应用程序的真实世界中，唯一真正“流行”的库仍然是——jQuery。(有些人也错误地将 Node.js 包含在他们的清单中，但是 Node 是一个运行时，所以它实际上不算)。

[](/jquery-will-still-be-around-long-after-angular-is-dead-bdedbc4550b9) [## Angular 死后，jQuery 仍然会存在很久

### 为什么这个成熟的 JavaScript 库仍然比以前更受欢迎！

javascript.plainenglish.io](/jquery-will-still-be-around-long-after-angular-is-dead-bdedbc4550b9) 

事实上，所有其他所谓的“流行”框架并不真的那么流行，也就是说，它们在 web 上的使用率不到 3%。React 的市场份额约为 3%，Angular 的市场份额约为 0.4%。大不了。

与此同时，据 W3Techs 的人说，jQuery 仍然是市场份额的领导者，拥有高达 95%的市场份额。

其他任何东西都无法与之相比。

我知道这确实激怒了一些为谷歌、脸书或其他大型科技公司工作的普通 JavaScript 纯粹主义者，但事实就是如此。Angular 希望它的受欢迎程度只有 jQuery 的十分之一。

关键是，不要浪费时间玩那些时髦的技术玩具，不要膨胀你的代码库，只使用每个人都在使用的东西 jQuery、Bootstrap 和你需要的任何其他丰富的控件。

更大的问题是，大多数这些时尚技术框架都是浪费时间，并不能真正节省您的时间——它们实际上只是增加了复杂性，并为您的项目增加了巨大的成本，这些成本是您一开始看不到的，也是您不必支付的。

如果你必须自己支付使用这些框架的费用，比如 Angular 和 React，你就不会使用它们。

[](https://beau-beauchamp.medium.com/why-you-should-stop-using-ui-frameworks-9289f0569a57) [## 为什么应该停止使用 UI 框架

### 我从事 web 应用程序开发已经超过 20 年了。我见过各种 UI 库来了也见过…

beau-beauchamp.medium.com](https://beau-beauchamp.medium.com/why-you-should-stop-using-ui-frameworks-9289f0569a57) 

# 结论

归根结底，也许 JavaScript 最终会取代所有其他语言的最大原因是，你我都已经知道了。每个人都知道如何用 JavaScript 编码——尤其是如果你的项目与网络有关的话。

Node.js 彻底打开了编程语言不断变化的局面，并为我们所有人提供了一个无处不在的平台和语言来进行交流，从浏览器客户端到 Lambda 服务，再到你能想到的每一个主要的桌面或服务器操作系统。

不，Java、PHP、Python、C#或任何你知道并喜爱的语言都不会完全消失，也许永远不会——但是 JavaScript 每年都在变得越来越强大。在某种程度上，JavaScript 将最终成为统治所有这些的一环！

____________________

*Beau Beauchamp 是一名 web 应用程序架构师，拥有 20 多年在云中开发企业级应用程序的经验；他是*[*WebTigers*](https://webtigers.com/)*的创始人，也是 Tiger 平台背后的首席开发者。*

*更多内容看* [*说白了。报名参加我们的*](http://plainenglish.io/) [*免费每周简讯*](http://newsletter.plainenglish.io/) *。在我们的* [*社区*](https://discord.gg/GtDtUAvyhW) *获得独家写作机会和建议。*