# 介绍 11 个核心 JavaScript 函数，它们将提高您的代码质量

> 原文：<https://javascript.plainenglish.io/introduction-to-11-core-javascript-functions-to-improve-code-quality-3b9843dad8ff?source=collection_archive---------16----------------------->

## JavaScript 无处不在，甚至在宇宙飞船中！提升你的技能&学习 11 个核心 JavaScript 函数，显著提高代码质量。

![](img/2b9954762a8906b942bb63c90d77c2eb.png)

它不在乎你是用后端还是前端工作(甚至是[飞船！JavaScript 可以在任何地方使用，因为它是一种非常灵活的语言。它具有核心的函数式编程模式和类，并且它与其他“类 C”语言的相似性使得每个开发人员都能轻松过渡。](https://www.infoq.com/news/2020/06/javascript-spacex-dragon/)

如果你想提高你的 JavaScript 技能，我建议你学习、练习并掌握这种语言中以下非常重要的核心函数。您不需要每个函数来解决大多数问题，但是在某些情况下，它们可以帮助您避免繁重的工作，而在其他情况下，它们会减少您必须编写的代码量。

# 地图()

最重要的 JavaScript 函数之一是`map()`！此外，这也是给学习 JavaScript 的人带来最大麻烦的一个函数。发生这种情况是因为这个函数的工作方式是从函数式编程中汲取的思想，而大多数开发人员并不熟悉这一点。在我们有偏见的大脑看来，这很奇怪，甚至是错误的。

功能`map()`很简单。它将自己附加到一个数组中，并将每一项转换成其他内容，从而生成一个新的数组。这种转换是由映射括号中提供的匿名函数完成的。

这就是地图的全部功能！

起初，`map()`的语法可能需要一些时间来适应，但是在掌握它之后，它将会是你使用 JavaScript 的最好的朋友之一。

## 为什么您可能想使用`map()`？

例如，假设我们记录了上周每天喷泉的水量，并将其存储在一个数组中。一周结束时，您被告知测量工具不够精确，水量比预期少了 3.2 升。

使用`map()`功能，您可以通过以下操作轻松解决这个问题:

当您从数组创建 DOM 元素列表时，您可以在 React 世界中找到另一个非常实用的例子。这是 React 中的一种常见模式，将通过这段代码来实现:

现在你可以争辩说`map()`只不过是`for`循环的另一个实现，你是对的，但是请注意，这可能是你受过面向对象训练的头脑做出的这一论断。

# 过滤器()

`filter()`是一个非常有用的 JavaScript 函数，您可以在许多情况下使用它，因为它根据给定的规则/逻辑过滤数组。这个规则/逻辑将作为匿名函数提供。

为了展示`filter()`是如何工作的，我们可以重用前面的喷泉例子。假设数组包含喷泉内储存的水量(**这次测量工具按预期工作**)。现在，我们想知道低于 36 升的数量有多频繁。这可以通过使用`filter()`功能来实现:

重要的是，您传递给`filter()`的匿名函数必须返回一个布尔值:`true`或`false`。`filter()`函数使用布尔表达式来确定是否应该在新生成的数组中插入一个值。

在匿名函数中，您可以实现任意数量的复杂逻辑来过滤数据；您可以读取用户输入，进行任何 API 调用，等等，只要您最终返回一个布尔值。

注意:记住`filter()`总是返回一个数组。如果过滤的数据为空，情况也是如此。这通常会导致代码片段中的细微错误，因为`filter()`是这样使用的:

你注意到什么了吗？最后的`if`条件检查`daysWithCriticalAmount`，它实际上是一个空数组，因为没有一天的水少于 30。

令人惊讶的是，如果您赶在截止日期之前，只想快速实现一个过滤方法，那么这个错误就太常见了。这段代码的问题在于，尤其是 JavaScript(是的，JavaScript 很奇怪)在许多方面是一种不一致的语言。有时事情的“真实性”就是其中之一。

你可能知道 JavaScript `[] == true`返回 false，你可能认为上面的代码是正确的。

**不幸的是，在一个** `**if**` **条件内，** `**[]**` **评估为真！换句话说，else 块永远不会被执行。**

修复这个问题非常容易，因为您只需检查结果数组的长度是否大于或等于 1。

# 减少()

与本文中的所有其他函数相比，`reduce()`正在争夺“令人困惑、怪异和复杂的 JavaScript 函数”的第一名。尽管这个函数非常重要，并且在许多情况下可以产生优雅的代码，但是许多 JavaScript 开发人员都避免使用它。他们更喜欢在没有`reduce()`的帮助下写代码。

原因之一是`reduce()`的复杂性。很难理解这个函数的概念和执行。此外，如果你读了它的描述，你必须重读几遍，但仍然会怀疑自己是否读错了(直到我看到它的运行时，我才意识到这一点)。

`reduce()`功能是用来减少(很明显不是吗？)将给定数组转换为单个值。这可能是一个数字，一个字符串，一个函数，一个对象，或者其他任何东西。

如果你想使用`reduce()`函数来简化一个数组，你需要通过提供一个函数来提供所需的逻辑。一般来说，这个函数将被称为 reducer 函数，它将第一个参数转换为`reduce()`。此外，它还包含第二个参数，该参数是一个起始值，可以是数字、字符串等。函数本身将如下所示:

**startValue:** 传递给`reduce()`函数的 startValue 是起始值(很明显...)用于要用 reducer 函数处理的计算。例如，如果你想执行加法，你可以从 0 开始，如果你想做乘法，你应该使用值 1。

**reducerFunction:** 如前所述，reducer 函数用于将数组转换为单个值。它有两个参数:一个`accumulator`和一个存储当前值的变量。

`accumulator`只是一个描述包含计算结果的变量的花哨名称(就像使用`total`对数组中的所有项求和)。在 reducer 函数中，累加器将被初始设置为起始值，然后通过数组逐步迭代执行计算，同时将每一步的结果保存在累加器中。

reducer 函数的第二个参数是`currentValue`，它将包含数组中特定步骤中给定位置的值。例如，在步骤 2 中执行 reducer 函数时，变量`currentValue`将包含来自输入数组的第二个值。

有了这些信息，我们应该看看下面的例子，它将在 reducer 函数中添加来自输入数组的每个值:

acc + currentValue"]，[0，[]，0，"将当前值与存储在累加器中的值简单相加。"]]]，[1，" p "，[[0，[]，0，"如果你用 for 循环做这个加法，它看起来像这样:"]]]]} ' >

在第一行中，我们定义了保存所有想要相加的数字的输入数组。下一行将包含`input.reduce()`调用，它将 acc 的起始值定义为 0，因为在加法中，我们应该从 0 开始，以免影响结果。减速器功能体`(acc, currentValue) => acc + currentValue`将当前值和存储在累加器中的值简单相加。

如果您用 for 循环做这个加法，它看起来会像这样:

正如您所看到的，简单的 for 循环示例要长得多，而且不如使用 reduce 那么优雅。

# 一些()

假设您有一个包含学生及其考试成绩的对象数组。现在，您想知道您的班级中是否有分数超过 90%的学生，而不关心是否有一个或多个学生以超过 90%的分数通过了考试。

如果您想在 JavaScript 中实现这一点，您可以使用一个循环和一个变量来解决问题，在找到第一个得分大于 90%的人后，将该变量设置为 true:

***对我来说，这段代码看起来非常“难看”、“啰嗦”，或者“恐怖”！***

它可以通过使用前面描述的`map()`函数来优化，但是这个解决方案还是有点笨拙。

幸运的是，JavaScript 有一个非常简洁的函数叫做`some()`，它在核心语言中可用，处理数组，并返回一个布尔值。在提供一个匿名函数的同时，它会过滤输入数组来很好地解决问题:

你可以看到它得到同样的输入，产生同样的结果，但是方式更优雅。此外，代码量减少，可读性比以前更好。

# 每隔()

JavaScript 核心语言中已经存在的另一个函数是`every()`。该函数将返回一个布尔值(如`some()`)，但将测试输入数组中的所有项目。为此，您必须(再次)提供一个匿名函数。例如，我们将测试每个学生是否都通过了考试，达到 70 分或以上:

像`some()`一样，这个函数创建简洁、易读、易维护的代码。

# 包括()

通常，如果我想检查一个数组中是否存在子字符串，我会使用`indexOf()`。不幸的是，我必须查找文档才能知道它们的返回值是多少。

幸运的是，JavaScript 中有一个很好的替代方法可以用来实现这一点:`includes()`。用法非常简单，而且区分大小写(我猜你也希望如此)。有关示例，请参见以下代码片段:

但是，includes 只能比较简单的值，不能比较对象:

# shift()

如果你想删除一个数组的第一个元素`shift()`是你应该使用的方法，因为它容易记忆和直观。注意，你也可以用`splice`来做这件事(稍后见)，但是`shift()`更简单:

正如您在这里看到的，shift 改变了它所调用的数组，并返回移除的元素。

**注意:** shift 的效率非常低，如果使用大型数组，应该避免使用它。在大型数组上调用太多的`shift()`会破坏你的应用程序！

# 未移位()

与删除一个元素的`shift()`相反，该函数用于在数组的开头添加一个新元素:

**注意:**和 shift 一样，unshift 的效率非常低，如果使用大型数组，应该避免使用它。在大型数组上调用太多的`unshift()`会破坏你的应用程序！

# 切片()

在 JavaScript 中存在一个被称为切片的概念，切片是通过提供起始索引和结束索引来创建包含原始字符串的一部分的新字符串的功能。现在，在 indexOf 函数的帮助下，您可以对输入字符串进行切片，以检索搜索到的子字符串:

请注意，开始索引包含在结果数组中，但结束索引不包含在结果数组中。此外，你可以看到“函数”和“that”之间的空间也没有切片。

此外，切片也可以用于数组:

# 拼接()

`splice()`听起来像`slice()`，可以和它进行比较，因为两个函数都从原来的数组或字符串创建新的数组或字符串。主要的微小但非常重要的区别是 splice()删除、更改或添加元素**，但修改原始数组**。如果您不完全理解 JavaScript 中的深度复制和引用是如何工作的，这种对原始数组的“析构”会导致巨大的问题！

以下示例将展示如何使用`splice()`:

这里可以看到`splice()`操纵了原始数组。如果你移除一个条目，它将返回移除的条目，但是如果你添加一个条目，返回的数组将是空的。

# 填充()

最后一个 JavaScript 函数是`fill()`,用于将几个项目更改为一个值，甚至将整个数组重置为初始值。如果你需要这个`fill()`可以帮助你避免循环来重置一个数组的值。此外，该函数可用于用给定值替换数组中的部分或全部条目。

您可以在下面的示例中看到它是如何工作的:

# 结论

这个列表包含了大多数 JavaScript 开发人员在职业生涯中遇到和使用的函数。虽然它很长，但它绝不是完整的，因为 JavaScript 中有太多更次要但非常有用的函数:`reverse()`、`sort()`、`find()`、`flat()`、`entries()`。我建议您阅读一下这些函数，因为您会在 JavaScript 项目中随时用到它们。

此外，只要有可能，您应该探索核心语言或著名的实用程序库，如 lodash，以加深您的 JavaScript 知识。这将导致巨大的生产力，你将学会创建更干净，紧凑，可读，可维护和可用的代码！

欢迎在我的[个人博客](https://www.paulsblog.dev)、 [LinkedIn](https://www.linkedin.com/in/paulknulst/) 、 [Twitter](https://twitter.com/paulknulst) 和 [GitHub](https://github.com/paulknulst) 上与我联系。

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)*和*[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*。查看我们的* [***社区不和谐***](https://discord.gg/GtDtUAvyhW) *加入我们的* [***人才集体***](https://inplainenglish.pallet.com/talent/welcome) *。*