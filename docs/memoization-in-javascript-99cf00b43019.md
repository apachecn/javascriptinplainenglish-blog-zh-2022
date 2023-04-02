# JavaScript 中的记忆化

> 原文：<https://javascript.plainenglish.io/memoization-in-javascript-99cf00b43019?source=collection_archive---------10----------------------->

## 什么是记忆，什么时候你应该使用它

![](img/1419b1af05e03b55dd63a20fe674ab61.png)

# 什么是记忆化

记忆化的概念是由 Donald Michie 和 K.B. Bennett 在 1965 年提出的，他们将其描述为“存储先前计算的值的艺术，以便以后可以快速查找。”

**JavaScript 中的 Memoization** 实际上是一种优化应用程序性能的技术，它存储昂贵的函数调用的结果，并在再次使用相同的输入时返回缓存的结果。这样可以节省时间，因为函数不必在每次调用时都执行:而是返回上次执行的结果。

为了更好地理解它是如何工作的，让我们来看一个代码示例。

# 代码示例

假设我们有一个非常低效的函数来计算一个数的平方。
该功能是故意低效的，以展示记忆的力量。

如果我们尝试使用这个函数来计算 15000 的平方，几秒钟后它就会给出结果。

如果我们重复这个操作，并且连续 5 次调用这个函数，每次都需要几秒钟来计算结果。

为了提高效率，我们可以使用 memoization:主要思想是存储以前的结果，所以如果我们用相同的输入连续几次调用这个函数，第一次仍然需要几秒钟才能给出结果，但是所有其他时间结果都会立即显示。这样，我们可以根据输入“缓存”值。

让我们看看如何实现这一点:

我们添加了一个变量`const previousValues = []`，它最初是一个空数组。
函数计算出结果后，我们将结果存储在这个`previousValues`数组的`number`位置，如下:`previousValues[number] = result`

现在我们可以添加一个 if 语句，说明如果`number`的值已经在`previousValues`数组中，那么只返回该值，否则计算它。

因此，如果我们再次尝试运行该函数，第一次仍然会很慢，但所有其他时间都是用相同的输入调用该函数，结果会很快返回。

这是记忆的一个完美的例子:你有一个需要很长时间执行的函数，你想反复得到相同的值。

# 何时何地使用记忆。

现在让我们来看看记忆化的一些实际应用。

*   **动态规划:**在动态规划中，你要解决很多子问题，然后把它们的结果组合起来。例如，著名的斐波那契数列就是一个动态程序的例子，其中每个结果都依赖于之前的结果(之前的数字)。这意味着，如果您需要多次进行这种计算，您不希望每次都重新计算所有这些中间值-您希望存储它们，以便它们只需要在输入发生变化时进行更新。记忆使我们能够做到这一点！
*   **Web 应用:**内存缓存在 Web 应用中被广泛使用，因为它可以显著提高性能，并通过减少不必要的计算来降低服务器负载。诸如 V8 或 SpiderMonkey 的 JIT 编译器(即时编译)之类的 JavaScript 引擎的能力在这里很有帮助，因为大多数现代浏览器在运行 JavaScript 代码时都在内部使用内存缓存，所以它们可以重用已经计算过的值，而不是在代码块/函数调用链的每次迭代中重新计算它们，这将是非常低效的，特别是对于大型数组或嵌套循环。

# 结论

我希望这篇文章已经帮助你理解了记忆化的概念以及如何在你自己的代码中使用它。内存化易于实现，并且在某些情况下可以极大地提高性能。

*考虑* [***成为中等成员***](https://ebelinggianmarco.medium.com/membership)**如果你喜欢看这样的故事，并且想帮助我这个作家。每月 5 美元，你可以无限制地访问媒体内容。如果你通过* [***我的链接注册，我会得到一点佣金。***](https://ebelinggianmarco.medium.com/membership)*

**更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们上*[***Twitter***](https://twitter.com/inPlainEngHQ)[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*[***YouTube***](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)**和* [***不和***](https://discord.gg/GtDtUAvyhW) *对成长黑客感兴趣？检查* [***电路***](https://circuit.ooo/) ***。******