# 我做代码评审时注意的事情

> 原文：<https://javascript.plainenglish.io/things-i-pay-attention-to-when-i-do-code-reviews-5699190ee12a?source=collection_archive---------7----------------------->

## 真的很简单，随时可以复制。

![](img/131de45d117e212ed41b8bff7716803c.png)

Photo by [Alvaro Reyes](https://unsplash.com/ja/@alvarordesign?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

代码审查是软件开发最重要的阶段之一。我注意到最近这个话题有点被忽视了。我会尽量回答最有争议的问题“如何做好代码评审”，或者给出一些提示。

软件开发的效率取决于许多因素。在其他事情中，它是团队合作(是否有冲突)或者任务被“重视”的程度

一个协调良好的团队允许自由交换意见。那就更容易说代码烂了。没有人会抱怨它，也许会动员起来写更好、更可读的代码。

# 大多数人都同意代码可以分为三类:

*   它可以工作，但是很难维护。这意味着任何重大的代码更改都会对现有功能产生负面影响。
*   它有效，并且易于阅读。这是任何公司都希望出现的理想情况。然而，这需要团队或程序员的高度自律。
*   以上两点的结合。可能是代码中最常见的情况。代码中有地方可以放在第一点和第二点。

同样，在代码审查阶段，代码将被定位在上述哪一个类别中。在我们的团队中，当每个人都接受代码时，合并就完成了。

# **那么如何做好代码评审呢？**

这里没有能解决所有问题的黄金法则。指导如何编写代码的公司标准会使它变得更容易。在前端的情况下，一些事情可以用工具来完成，比如更漂亮的或者各种类型的衬垫。不幸的是，这些附加组件负责代码的可视部分。它们不会取代人的因素。

# **将代码返回到代码审查中可以做什么？**

*   考虑代码读起来好不好，能不能写出更好或者更短的东西。文件是否在正确的位置，是否对齐？或者有些东西可以被分离或者变得有用？
*   不要把所有的事情都当成一个大的承诺。尽可能将代码分成小块。变化越少，分析就越容易。之后就可以按照变化的过程来了。
*   向代码中添加描述解决方案的注释。这样，另一边的人将能够理解你的意图和改变的原因(背景)。在这种特殊情况下，建议的解决方案可能是最佳的。
*   当对代码进行修改时，不要将它们作为 cr 修正提交！它什么也没说。描述代码的实际变化。(专业提示:如果您对代码进行了更改，您可能希望在提交消息之前进行重构，这在这里将会非常有效。

# **当你被要求进行代码审查时，该怎么做？**

# **1。可能的话，速战速决**

代码审查只是整个软件开发过程的一部分。这样的代码仍然需要 QA 来测试。你等待完成这项任务的时间越长，你就越阻碍这个过程。当然，如果代码量更大，五分钟也是知道查不完“拍拍”的。

# **2。代码好看吗？**

传递给函数或组件的参数是否过多？这段代码做了它需要做的事情吗？它在正确的地方吗？或者可能一个条件太复杂，有些东西要简化？或者也许变量或函数的名字不是最好的命名？所有这些(可能还有其他一些东西)都会影响代码的质量和维护。

# **3。本地运行代码**

检查团队成员是否正确地实现了功能或纠正了错误是一个非常好的习惯。一切都正常工作了吗，基本案例都包括了吗？在我们公司，在提交代码进行测试之前，团队中的另一个人(不是 QA)必须检查所有的东西都被正确实现了。由于这一点，我们减少了以后出现错误的机会。

# **4。测试！**

检查代码是否已经被测试覆盖是很好的(甚至有机器可以做到这一点)。我知道困难是不同的，取决于很多因素。这一点值得关注。

用测试覆盖代码，即使是那些难以维护的测试，也会部分地减少以后的问题。如果有测试，那就值得关注其中的内容，是否有意义。React 组件(或 CSS 样式)的快照是否足够？

# **5。创建一个专门的会议来讨论代码或问题。**

代码会议在我目前的团队中非常有效。他们每个人都展示了他做了什么和为什么。然后大家提问，变成有趣的讨论。我们之前写了很多评论，但是对于更复杂的问题效果并不好。这样的会议是一个现场编码(或结对编码)的好时机，在这里我们一起解决一个给定的问题。

老实说，当我站在代码审查的一边或另一边时，我会注意这些类型的事情，并且它一直工作，没有痛苦。

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*[***YouTube***](https://www.youtube.com/channel/UCtipWUghju290NWcn8jhyAw)*[***不和***](https://discord.gg/GtDtUAvyhW) *。***