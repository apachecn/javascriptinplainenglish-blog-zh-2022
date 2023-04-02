# 承诺到底是什么？

> 原文：<https://javascript.plainenglish.io/what-exactly-is-a-promise-601c6f39a8ad?source=collection_archive---------5----------------------->

## 让我们结束困惑(希望如此)。

![](img/2a0cb315f2bba5806e1005a1ec39773e.png)

Photo by [OSPAN ALI](https://unsplash.com/@ospanali?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

通常，当一个人想了解更多关于一个概念的信息时，他们可以在谷歌上搜索，点击第一个结果，几秒钟内就可以得到他们需要的信息来更好地理解它。有时候没那么容易。某些主题甚至需要挖掘多个来源才能开始理解它们。搜索 JavaScript promise 将会返回如下内容:

*承诺是代表异步操作最终完成或失败的对象。*

并且:

承诺是一个特殊的 JavaScript 对象，它将生产代码和消费代码链接在一起。”

嗯……好吧，我知道我不是最锋利的工具，但我愿意打赌，除了我之外，很多人都必须做更多的挖掘，以获得更好的承诺。这就是为什么我们要看一看 JavaScript 中的承诺，并希望在结束时对它们有一个坚定的理解，而不必浏览无数的文档和文章。

JavaScript 通常同步执行。也就是说，它运行一行代码，当它完成执行时，它运行下一行。

这段代码是同步的，因为`knock knock`总是在`who's there?`之前登录到控制台。缺点是，如果一个特定的任务语句被求值，那么程序的其余部分将被冻结，直到它被完成。由于大量的 web 应用程序从 API 获取数据，所以在做其他事情之前必须等待编译完成是不方便的。为了补救这一点，有许多 Web APIs 可用于异步工作的方法。

让我们快速看一下一个叫做`setTimeout()`的异步方法。它为第一个参数接收一个回调函数，并以毫秒为单位接收一个可选的时间参数。

当调用该方法时，计时器根据第二个参数启动，这里是 3 秒。一旦定时器结束，回调函数就会执行。注意，其他代码行在`setTimeout`完成之前执行。这就是异步 JavaScript！

当异步函数存在时，为了控制程序的流程，通常的做法是链接回调函数。回调链内的任何东西都将在异步部分执行后运行，而链外的任何东西都不会受到影响并立即执行。这改善了流动，但有一个巨大的缺点。

链外的代码行将立即执行。将回调函数链接在一起可以让数字按顺序计数，彼此相隔三秒。它的作品，但哇是很难阅读。这就是所谓的“回调地狱”。这也只是一个 3 部分链，所以想象一个有 10 个或更多部分。呀，光是想想就让我头疼！

为了更好地处理异步动作，请参见`Promise`。像 JavaScript 中的其他东西一样，`Promise`是一个对象。根据现在已知的情况，让我们再来看看之前的一个定义:

*“承诺是代表异步操作最终完成或失败的对象。”*

通俗地说，承诺是为异步操作创建的对象。在创建时，promise 对象不包含任何值，并且正在等待数据。如果异步操作成功完成，那么返回的数据将被设置为 promise 对象中的值。如果失败，则它保存一个错误，该错误可用于显示通知用户失败的消息。承诺有三种状态:

1.  **pending** :承诺创建时的初始状态，等待异步操作的结果。
2.  **已完成**:异步操作已成功完成，返回的数据现在保存在承诺中。
3.  **拒绝**:异步操作失败，承诺中存在错误。

Promise 对象是用`new`关键字创建的，并以两个函数作为参数。一个用于处理成功的异步操作，另一个用于处理失败。

当新的承诺对象被创建时，它处于`pending`状态，直到`resolve`或`reject`功能被调用，然后状态相应地切换到`fulfilled`或`rejected`。用承诺控制程序流是通过从`Promise`原型继承的两个方法实现的:`then()`和`catch()`。这些方法允许将承诺链接在一起，以便在异步操作完成后可以直接采取进一步的操作。让我们看一个模拟从 API 获取数据的例子。

这个函数创建一个承诺，如果数据是真的，那么这个承诺就被实现，如果数据是假的，那么这个承诺就被拒绝。这里使用`setTimeout()`函数来模拟类似于从 API 抓取数据的延迟。

让我们解开这段代码。执行`fetchData()`函数并创建一个新的承诺对象。它的状态是`pending`，因为它在等待异步操作的结果。当`setTimeout()`被调用时，计时器开始计数，跟随`fetchData()`的代码将开始执行。`I will not be delayed`被登录到控制台。一旦计时器结束，promise 将检查数据是否真实。给`fetchData()`的`1`的自变量为真，因此承诺被解析，状态变为`fulfilled`，承诺的值也为`1`。使用`then()`链接承诺。每次调用`then()`都会创建一个全新的处理值的 promise 对象。首先，将原始承诺的值记录到控制台:`1`。然后数值翻倍:`2`。然后，再一次，值翻三倍:`6`。承诺状态是`fulfilled`，所以`catch()`在这里不返回任何东西。欢迎来到所谓的“承诺链”。它控制从异步操作中获得的数据流，程序的其余部分可以无延迟地运行。它读起来也干净得多，看着它也不会让人头疼。不错！

`catch()`方法也创建了一个`Promise`的新实例，但是没有一个案例被解析。当异步操作失败时`catch()`返回一个包含错误的承诺对象。

这里`fetchData()`被无参数调用。由于这评估为假，承诺对象的状态改变为`rejected`并且`catch()`将错误信息记录到控制台。

这就是`fetch()`方法的基本工作原理。它是另一个 Web API 异步方法，从其他 API 获取(natch)数据。从 URL 收集资源，并返回可以链接的承诺。

承诺是处理异步请求的重要部分。它们使得在不停止应用程序其他部分工作的情况下收集天气、新闻和股票信息等数据成为可能。随着`fetch()`成为网络应用程序的重要组成部分，了解承诺是什么以及如何使用它们来控制应用程序中的数据流是至关重要的。

*更多内容尽在* [***说白了. io***](https://plainenglish.io/) *。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于* [***推特***](https://twitter.com/inPlainEngHQ) *和*[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*。加入我们的* [***社区不和谐***](https://discord.gg/GtDtUAvyhW) *。*