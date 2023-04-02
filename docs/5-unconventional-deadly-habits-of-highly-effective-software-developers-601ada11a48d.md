# 高效软件开发人员的 5 个非常规致命习惯

> 原文：<https://javascript.plainenglish.io/5-unconventional-deadly-habits-of-highly-effective-software-developers-601ada11a48d?source=collection_archive---------21----------------------->

## 传统的测试，比如 DRY、Write 单元测试和 KISS 不包括在内

![](img/761b1da317831648e9a5fc65fc1e9f6f.png)

Photo by [Pavel Danilyuk](https://www.pexels.com/@pavel-danilyuk?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) from [Pexels](https://www.pexels.com/photo/smiling-man-wearing-a-t-shirt-with-hoodie-8422813/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)

脸书首席执行官马克·扎克伯格有每天穿同样衣服的习惯。

这个习惯帮助他节省精神能量来做重要的决定。他不想浪费他的精神能量来决定每天穿什么。

有一次我发现了祖克伯格每天穿同一件衣服的心理，我觉得这是一个创业者致命的标新立异习惯之一。

在那之后，我开始寻找高效软件开发人员的一些非常规的致命习惯。这些是我发现的事情。

# 1.他们提出一些小的拉取请求

高效的开发人员不喜欢发出大的拉取请求。

代码评审者可以很容易地对小的拉请求提供反馈。代码审查者不想一次检查 400-500 行代码变更。

他们中的大多数人想要检查 100 到 150 行长的代码变更。如果您是一名习惯于发出大量拉取请求的开发人员。改变它。否则，评审者会强迫你提出小的拉取请求。

效率低下的开发人员习惯在沉默中工作数周。一旦他们安静地完成工作，他们会提出一个大的拉请求。审阅者很难处理如此多的更改。

评审者要求他们将大的拉取请求分成较小的请求。

只有到那时，他们才同意审查它。

# 2.情感上脱离他们的准则

对软件开发人员来说，不要对你的代码感情用事是一种超能力。高效的软件开发人员永远不会对他们的代码和设计产生情感依恋。

如果他们在过去编写了不再适用的代码。他们准备把代码扔进垃圾桶。

有效的开发人员不会像对待自己的孩子一样对待他们的代码。代码只是一个负债，感觉没什么。他们很明白这一点，如果不再需要就愿意扔掉。

简单地依赖他们的代码。它们使得代码审查者的工作更加容易。代码评审者分享的评论是认真对待的。

如果审查者要求删除特定的代码段并重写它。他们只是不开始与评论家争论。

首先，他们分析自己写的代码。如果他们发现评论者的评论是真实的。他们愿意放弃他们的代码，即使他们花了两年时间来写它。

# 3.他们习惯不写聪明的代码

有效的开发人员更喜欢清晰而不是聪明。有效的开发人员不会写聪明的代码，因为它很难阅读。当你的代码可读性高时，你从评审者那里得到的反馈是好的。

代码评审员认为开发人员重视他们的时间。这就是为什么他们试图给出诚实的反馈。

有效的开发者并不是不知道把十行代码转换成一行的窍门。尽管如此，他们避免使用所有的伎俩。他们知道使用那些伎俩只会给未来带来麻烦。

让我们举个例子来理解这一点。

## 交换两个数字 a 和 b

```
a ^= b;b ^= a;a ^= b;
```

如果你用这种方法交换两个数。只有少数看过你代码的程序员才会明白这一点。如果您在代码库中使用了这个技巧，代码的可读性会降低。

但是如果你用上面的方法交换数字，任何程序员都能够理解。以下代码提高了代码的可读性。

```
int temp = a;a = b;b = temp;
```

任何阅读你的代码的程序员，无论是你的代码审查员还是未来维护项目的开发人员。他们会很容易理解上面的代码，因此不会面临问题。

它不仅使审查者的生活变得更容易，也使未来的开发者的生活变得更容易。

# 4.他们不会写不必要的评论

额外评论。额外的头痛。

代码中注释的唯一目的是解释您的逻辑。如果你写注释让你的代码看起来漂亮。删除它。

如果注释让你的代码难以阅读，那就完全没有必要写注释。很多时候，我阅读开发人员编写的代码，发现没有注释的代码很容易阅读。

如果你需要写注释来解释每一行代码。你做错了。不要用你无用的注释来复杂化代码库。

只是一个小例子。

```
temp--; // Decrementing the value of the variable temp
```

你真的想写像上面这样的评论。

```
temp--;
```

告诉我一件事。

如果你刚刚开始学习编程。你难道不明白递减运算符的作用是什么吗？为什么任何开发人员都需要添加注释来解释递减运算符的作用。

一个有效的开发人员从不编写包含不必要注释的代码。他们的目标是编写易读的代码。

# 5.根据任务的优先级安排任务

知道任务优先级的软件开发人员工作效率更高。

一个开发人员每天都会收到来自团队中不同人的无数电子邮件和垃圾消息。包括同事寻求帮助、经理请求更新、参加会议以及修复错误。

这些事情中的大部分，包括电子邮件、休闲裤和会议，都是为了偷走你的时间。您收到的每个通知都有相关的紧急程度。但实际上，最紧急的是已经分配给你的任务。

电子邮件和信息之类的东西只是不必要的干扰。这些东西只是作为压力助推器。

如果你深入挖掘和分析，大多数时候开发人员错过了他们的最后期限，因为他们在做紧急但不重要的事情。

想象一下。

假设您正在为应用程序添加一个新特性。突然，通过电子邮件，你被要求紧急修复代码库中的一个 bug。你放下分配的工作，去修复 bug。

第二天，在工作时，你被要求参加一个会议。一天后，一位同事向他寻求帮助。紧急的事情不断的来，你的工作不断的迟到。

如果你不清楚你的优先权，你作为一个开发者就不会有成效。你会发现所有有效的开发人员都清楚他们的优先级。

他们从不在紧急但不重要的事情上花费过多的精神精力。如果有紧急情况出现，比如开了几个会，即使是在会上，他们也会努力节省精神能量。

一旦你开始按照优先顺序工作，你就不需要任何时间管理技巧来让你的日子富有成效。

# 摘要

1.  提出小的拉动请求。
2.  不要对他们的代码产生感情。
3.  他们有一个不写聪明代码的习惯。
4.  不要写不必要的评论。
5.  根据任务的优先级安排任务。

# 想联系作者？

加入一个人人社区，欣赏与科技相关的文章。我们讨论最新的技术和独特的见解。

新读者可以注册阅读我的故事&我会收到他们的一部分会员费。更多信息请访问 https://sanjay-priyadarshi.medium.com/membership

[](https://sanjay-priyadarshi.medium.com/membership) [## 通过我的推荐链接加入 Medium-Sanjay Priyadarshi

### 作为一个媒体会员，你的会员费的一部分会给你阅读的作家，你可以完全接触到每一个故事…

sanjay-priyadarshi.medium.com](https://sanjay-priyadarshi.medium.com/membership) 

*更多内容看* [***说白了就是***](http://plainenglish.io/) *。报名参加我们的* [***免费周报***](http://newsletter.plainenglish.io/) *。在我们的* [***社区获得独家访问写作机会和建议***](https://discord.gg/GtDtUAvyhW) *。*