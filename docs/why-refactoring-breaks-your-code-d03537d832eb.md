# 为什么重构会破坏你的代码

> 原文：<https://javascript.plainenglish.io/why-refactoring-breaks-your-code-d03537d832eb?source=collection_archive---------1----------------------->

## 如何在不破坏一切的情况下进行重构。

![](img/09f45beb44c515066ff1d036542c693f.png)

Photo by [Andrew Roberts](https://unsplash.com/@ar1428?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

重构是软件开发人员的一项重要技能。尤其是在实现应用程序的时间敏感部分时，通常没有足够的时间来考虑架构的每个细节。此外，用不熟悉的需求开发特性是糟糕代码的常见来源。最重要的是，代码的质量取决于团队的整体技能水平。我们必须和初级员工一起工作，有时甚至要继承他们的代码库。不要误解我:我们都有开始的时候。但不幸的是，这并不总是我们能够解释的事情。

然后，我们坐在一起计划如何改进我们的代码。每个人都被炒作。最初的动机迟早会屈服于彻底的放弃，原因有几个:

*   要重构的东西太多了；你不知道从哪里开始，如何开始。
*   你的重构产生了错误。
*   在重构的时候，你仍然需要改进代码库。所以你必须在改进代码库的同时编写新的特性。
*   重构不知何故让一切变得更糟。

如果这听起来对你来说很熟悉，让我们一个一个地检查问题，并找出下次如何做得更好。

## 从哪里开始重构？

我能理解那些试图以任务的形式协调重构的团队。然而，在进行过程中进行重构是有益的。Robert C. Martin 说最好应用探路者原则:让代码比你发现时更干净。换句话说，让重构成为一种习惯，成为你日常工作的一部分。当第一次开始适应重构时，尝试一下子重构所有的东西是很诱人的。不要那样做。它很可能会失败。

在开始重构你的代码之前，确保你*满足需求，*这意味着:你的代码应该被自动化测试覆盖。

你可能会问:“为什么我需要测试？我自己考。”
测试确保你的项目的商业价值得到满足。例如，如果你在你的网站上卖书，你想确保购买你的产品的过程是有效的。因此，您创建用户测试(端到端测试)来覆盖真实的用例。这将确保你的用例保持完整，不管你做了什么改变。否则，您将不得不一次又一次地手动测试整个应用程序。根据项目的规模和复杂程度，这是不现实的。然后你*需要*自动化测试就位。

这也是为什么测试是重构的一个需求。他们将确保你的代码*不会破坏*。所以，如果你还没有测试，那么在重构之前**覆盖你的代码**。这将确保商业价值不受影响。

拥有一个经过良好测试的代码仍然不意味着你可以马上重构。还有一些问题需要回答:你想改善什么？涉及哪些文件？所有相关文件/模块/组件的总体目标是什么(例如，目标体系结构)？诸如此类。不要急于求成，尤其是在你还没有任何经验的时候。相反，创建一个所有人都同意的计划，这样就没有一个人对重构的内容承担所有责任。这里有一个例子:

1.  根据用例对文件中的所有功能进行分组(例如，使用区域)。我建议这样做，尤其是对于大文件。
2.  现在您应该有一个包含不止一个用例的文件。您可以与您的团队讨论这一点，并采取以下行动。
3.  这可能意味着您选择一个用例，并将其提取到它自己的文件中。
4.  完成一个模块后，你可以与你的团队讨论结果。有什么收获吗？一切顺利吗？
5.  然后，您可以继续从该文件中选择下一个用例，或者获取下一个文件。

对于包含大量文件的复杂项目，这是我最喜欢的例程之一。

TLDR，尤其是在团队工作时，不要独自重构。做结对。利用你团队的专业知识。让每个人都参与进来。这是一种可以改变整个团队对代码质量态度的学习。

## 你的重构会产生错误

正如上一章提到的，重构的一个要求是测试到位。如果你在测试和重构方面没有经验，你仍然会产生错误。这很常见，所以不要因此而沮丧。你*需要*套路。评估这些错误，并找出如何避免它们。不要只是修复和忽略它的发生。接受学习需要时间；没有人第一次做得完美。

如果你在一家没有错误文化的公司工作，也不会给错误提供任何空间，赶紧离开那里。如果你因为害怕犯错而从不采取行动，你会停滞不前，什么也学不到。

## 在重构的时候，你仍然需要在项目上取得进展

项目经理不喜欢重构，因为它们通常意味着项目没有进展。作为一名开发人员，在重构完成之前，你通常不会有机会暂停整个项目。所以，你必须在改进代码的同时处理一个正在进行的项目。

为了解决这个问题，你必须让整个团队适应重构的习惯。探路者原则是解决这个问题的一种方法。为了支持这一点，您还应该有一个适当的代码审查实践。代码评审应该有一个目标:支持开发人员尽快部署特性，尊重一致同意的代码质量度量。不要在代码评审中讲授(记住它，在正确的时间做)，不要不必要地停止开发，不要责怪任何人。失败的代码审查是过程的问题，而不是开发人员的问题。改进流程；开发者会自动变得更好。代码审查的结果应该是可预测的。代码审查是检查每个团队成员是否适应探路者原则的一个很好的方法。

取决于你的团队，这可能需要一段时间，并伴随着一些起伏。但是，最终，这是值得的。

就这些了，伙计们。

感谢您的阅读。

*更多内容请看*[***plain English . io***](https://plainenglish.io/)*。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。关注我们关于*[***Twitter***](https://twitter.com/inPlainEngHQ)*和*[***LinkedIn***](https://www.linkedin.com/company/inplainenglish/)*。查看我们的* [***社区不和谐***](https://discord.gg/GtDtUAvyhW) *加入我们的* [***人才集体***](https://inplainenglish.pallet.com/talent/welcome) *。*